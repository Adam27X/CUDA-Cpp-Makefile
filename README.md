# CUDA-Cpp-Makefile
Makefile prototype for large CUDA C++ Programs

Programs using a mix of CUDA and C++ source files are difficult to manage using Make.
nvcc requires files to end in a .o suffix for linking, but Makefile rules ending in .o overwrite
existing implicit rules, causing annoying circular dependency messages.
Furthermore, the nvcc compiler is slow, especially for the compilation of large projects. 
Hence, solutions that recompile all CUDA source files even though only a small number have changed are inadequate.

This simple Makefile handles these annoyances automatically.

Input:

- Directories containing C++ and CUDA source files, and (optionally) CUDA header files
- C++ and CUDA include directories
- g++ and nvcc compiler flags (one can easily adjust for Clang if desired) 
- (Optionally) Debug equivalents of the above

Output:

- A compiled and linked executable of your code
- Source files are treated separately - editing of just one file requires recompilation of only that file
- A makefile for CUDA/C++ projects that "just works" as expected

-------------------------------
Notes: There is room for improvement here, but this approach has worked well for my projects, so I wanted to share it.

-Adam McLaughlin
