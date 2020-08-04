# C Cheat-Sheet

## Requirements (one way)
- Install Visual Studio (any edition)
- Create Taskbar Shortcut for "Developer Command Prompt for VS?"

## Compilation
- Compile all c files (creates .obj files) 
  - > cl *.c /W4
  - /W4 flags compiler to compile more strictly
- Link all obj files (creates executable)
  - > link *.obj /out:my-c-app.exe
  - "link" pulls together the file dependencies under a single executable
