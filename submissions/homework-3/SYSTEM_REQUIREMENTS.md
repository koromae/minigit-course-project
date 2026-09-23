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
