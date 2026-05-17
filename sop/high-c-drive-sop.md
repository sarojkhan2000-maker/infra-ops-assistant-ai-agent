# High C Drive Usage SOP

## Purpose
This SOP explains what to do when a Windows server C drive is running high on space.

## Symptoms
- C drive usage is high
- Server may become slow
- Applications may fail to write temporary files or logs

## Recommended Action
1. First clear files from C:\Temp.
2. If the issue continues, check and clear C:\Logs.
3. Do not delete Windows system folders.
4. Always ask for approval before cleanup.

## Approved Cleanup Folders
- C:\Temp
- C:\Logs

## Do Not Delete
- C:\
- C:\Windows
- C:\Program Files
- C:\Program Files (x86)
- C:\Users
- C:\ProgramData

## Approval Rule
Before deleting files, always ask the user for confirmation.