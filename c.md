# C Cheat-Sheet

## Requirements (one way)
- Install Visual Studio (any edition)
- Create Taskbar Shortcut for "Developer Command Prompt for VS?"

## Compilation
- Compile all c files (creates .obj files) 
  - cl *.c /W4
  - /W4 flags compiler to compile more strictly
- Link all obj files (creates executable)
  - link *.obj /out:my-c-app.exe
  - "link" pulls together the file dependencies under a single executable

## Variables
- Variables in C are strongly typed
  - int someNumber = 5;
- Strings require library extension
  - ```#include <string> ```
- Static variable declarations cause the value to persist
  - static string someString = "hello Sam!";
- Beware: Variables remain on the stack after function execution
  - Variables remain in scope (I think), but do not get cleared unless they are "trampled" by another declaration
- Variables declared outside of a function are scoped to the entire file
  - Always declare such file-scoped variables as "static" and with an initial value, to avoid stack-trampling
