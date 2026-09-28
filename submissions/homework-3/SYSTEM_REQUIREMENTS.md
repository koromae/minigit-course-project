## Approved UN/UR Baseline

# Approved MiniGit user needs and user requirements

This instructor-approved baseline is the starting point for Homework 3. Homework 2 was practice; students should keep their HW2 work, but use the stable IDs below for HW3–HW6. These statements describe the user's goal and visible capability. They do not specify storage files, hashing, classes, or algorithms.

## Project boundary

MiniGit is a local educational version-control tool. It supports `init`, `status`, `diff`, `diff --staged`, `add <file>`, `commit -m <message>`, and `log`. It does not implement branches, merging, network operations, GitHub, or Pull Requests. Students use real Git/GitHub for class collaboration.

## User needs

| ID | Stakeholder need |
|---|---|
| UN-GIT-01 | A student developer needs a way to start tracking a local project because it has no recorded history. |
| UN-GIT-02 | A student developer needs to know which project files have changed because they may forget what they edited before recording a checkpoint. |
| UN-GIT-03 | A student developer needs to inspect changed content before recording it because a file may contain unintended edits. |
| UN-GIT-04 | A student developer needs to choose the file content to include in the next checkpoint because later edits may still be unfinished. |
| UN-GIT-05 | A student developer needs to record a meaningful checkpoint because they want to preserve a known project state and explain its purpose. |
| UN-GIT-06 | A student developer needs to review earlier checkpoints because they want to understand how the project reached its current state. |
| UN-GIT-07 | A student developer needs invalid commands to explain why they failed while preserving existing project files and recorded checkpoints. |

## User requirements

| ID | User-visible capability | Need |
|---|---|---|
| UR-GIT-01 | A student developer shall be able to initialize tracking in the current local project folder without removing existing project files. | UN-GIT-01, UN-GIT-07 |
| UR-GIT-02 | A student developer shall be able to see whether project files are untracked, staged, changed after staging, modified, deleted, or clean. | UN-GIT-02 |
| UR-GIT-03 | A student developer shall be able to view differences between current working file content and the content selected for the next checkpoint. | UN-GIT-03 |
| UR-GIT-04 | A student developer shall be able to view differences between content selected for the next checkpoint and the latest recorded checkpoint. | UN-GIT-03 |
| UR-GIT-05 | A student developer shall be able to select the current content of one existing project file for the next checkpoint without selecting unrelated files. | UN-GIT-04 |
| UR-GIT-06 | A student developer shall be able to create a checkpoint of selected content with a nonempty explanation while leaving later unselected edits in the working files. | UN-GIT-05, UN-GIT-04 |
| UR-GIT-07 | A student developer shall be able to view recorded checkpoints from newest to oldest, including their identifier and explanation. | UN-GIT-06 |
| UR-GIT-08 | A student developer shall receive a useful error when a command is invalid, a requested file is unavailable, or a path is outside the allowed project files. | UN-GIT-07 |
| UR-GIT-09 | A student developer shall be able to retry an operation after a failure without losing ordinary project files or an already recorded checkpoint. | UN-GIT-07 |

## Worked relationship example

`UN-GIT-04` explains why selection matters. `UR-GIT-05` grants the user the capability to select one current file. A student may derive a system requirement that `add <file>` copies that file's current content into a stage area and does not include another file. They may then write an acceptance test that stages `notes.txt`, edits it again, and checks that the staged copy still contains the earlier content. The system requirement and test are examples of the next level; they are **not** part of this approved user baseline.

## Clarification of UN-GIT-07

This need concerns **failure handling before a mistaken command takes effect**, not an `undo`, `revert`, or restore feature. For example, `add missing.txt` should report an error without changing an existing staged copy; `commit -m ""` should report an error without changing the latest checkpoint. The user may correct the input and retry. Recovering an earlier file version after a successful commit is outside this MiniGit scope.

## Baseline use rules

1. Copy these nine UR IDs and seven UN IDs into the HW3 baseline section without renumbering.
2. A system requirement may support more than one UR; every UR must have at least one supporting system requirement.
3. Derive observable system behavior and verification; do not copy a UR and merely replace “student developer” with “system.”
4. If a student identifies a genuine ambiguity, record a proposed clarification and use the instructor's approved wording for grading until a published update is issued.

## UR-to-UN Mapping
UR-GIT-01 → source UN ID(s): ___UN-GIT-01__
UR-GIT-02 → UN-GIT-02 (worked example)
UR-GIT-03 → source UN ID(s): ___UN-GIT-03__
UR-GIT-04 → source UN ID(s): __UN-GIT-03__
UR-GIT-05 → source UN ID(s): __UN-GIT-04__
UR-GIT-06 → source UN ID(s): ___UN-GIT-04__, ___UN-GIT-05__
UR-GIT-07 → source UN ID(s): __UN-GIT-06__
UR-GIT-08 → source UN ID(s): ___UN-GIT-07__
UR-GIT-09 → source UN ID(s): __UN-GIT-07__



## Functional System Requirements

Under that heading, write FIVE numbered SRs in your HW3 file. Use the following exact topics in order: SR-01 first init; SR-02 repeated init; SR-03 add one existing file; SR-04 add a missing file; SR-05 status for one staged file. For EACH SR, write its source UR ID, starting condition, action, and observable result. Do not merely repeat the UR. Use this frame: “SR-__ (source UR-GIT-__): Given [state], when [exact MiniGit command], MiniGit shall [result that a classmate could check].” The worked SR-03 below may be adapted in your own words.
Worked SR-03: Given an initialized project with notes.txt containing ONE and plan.txt present, when add notes.txt is used, MiniGit shall stage a copy of notes.txt containing ONE without staging plan.txt.

- My SR-01 result I can check: __Given an initialized project with notes.txt containing ONE and plan.txt present, when init is used for the first time, the Minigit shall create an empty local git repository ___

- My SR-02 result I can check: ___Given an initialized project with notes.txt containing ONE and plan.txt present, when init is used for the second time, the Minigit shall deliver an error message and impeach the action to alter or change any file in the project__

- My SR-04 error and preserved state: _Given an initialized project with notes.txt containing ONE and plan.txt present, when add missing.txt file is used, the MiniGit shall display an error message and impeach the action to alter or change notes.txt, nor plan.txt in the project folder.___

- My SR-05 result I can check: _Given an initialized project with notes.txt containing ONE and plan.txt present in the project folder, when checking for the status of one staged file, the Minigit shall clearly display the modified file ready for the next checkpoint, which indirectly confirms that other unintended files have not been mistakenly selected for the said checkpoint.___


- SR-01 → source UR ID(s): __UR-GIT-01__
- SR-02 → source UR ID(s): __UR-GIT-08__, __UR-GIT-09__
- SR-03 → source UR ID(s): ___UR-GIT-05__
- SR-04 → source UR ID(s): __UR-GIT-08__, __UR-GIT-09__
- SR-05 → source UR ID(s): __UR-GIT-02__ , ___UR-GIT-05__
One concrete “Check:” from my HW3 file: ______________________
____________________________________________________________





## 12 System Requirements


- My SR-01 result I can check: __Given an initialized project with notes.txt containing ONE and plan.txt present, when init is used for the first time, the Minigit shall create an empty local git repository ___

- My SR-02 result I can check: ___Given an initialized project with notes.txt containing ONE and plan.txt present, when init is used for the second time, the Minigit shall deliver an error message and impeach the action to alter or change any file in the project__

- My SR-03:

- My SR-04 error and preserved state: _Given an initialized project with notes.txt containing ONE and plan.txt present, when add missing.txt file is used, the MiniGit shall display an error message and impeach the action to alter or change notes.txt, nor plan.txt in the project folder.___

- My SR-05 result I can check: _Given an initialized project with notes.txt containing ONE and plan.txt present in the project folder, when checking for the status of one staged file, the Minigit shall clearly display the modified file ready for the next checkpoint, which indirectly confirms that other unintended files have not been mistakenly selected for the said checkpoint.___

- My SR-06: _Given an initialized project with notes.txt containing ONE and plan.txt present in the project folder, the Minigit should clearly show the content that is selected for the next checkpoint from the content not selected and still saved in the working tree. When the appropriate command is run, the minigit must distinctly diplay the files in the staged area, and the file still in the working area without confusion and alteration.

- My SR-07: _Given an initialized project with notes.txt containing ONE and plan.txt present in the project folder and having a recorded checkpoint, the minigit should 

- My SR-08: Given an initialized project with notes.txt containing ONE and plan.txt present in the project folder, when the command “ git commit -m “…” “ is ran, the minigit should create a descriptive checkpoint without altering any other files that was not selected for the checkpoint, in other words any file that was not explicitly staged. 

- My SR-09: Given an initialized project where notes.txt is staged with "ONE" and then modified in the working tree to "TWO", when diff is used, MiniGit shall display the line-by-line differences between the working file and the staged copy in the terminal output.

- My SR-10: Given an initialized project with two recorded checkpoints having unique identifiers and descriptions, when log is used, MiniGit shall display the checkpoints from newest to oldest, showing each checkpoint's identifier and explanation.


- My SR-11: - My SR-11: Given an initialized project with notes.txt staged, when commit -m "" is used with an empty explanation string, MiniGit shall display a descriptive error message and leave the staged content and latest checkpoint unchanged.

- My SR-12:  Given an initialized project, when an invalid command or a file path outside the allowed project files is used, MiniGit shall display a clear error message without altering any existing project files or recorded checkpoints.