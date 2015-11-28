# Programming challenges

Random ideas for projects. Feel free to submit pull requests adding more, the only requirement is being neither useful nor realistic ;) Please let me know if you manage to do one of these and I'll add a link to your source.

## Implement RFC5841 - TCP option to denote packet mood

Embedding the mood itself should be easy enough, but there are a lot of details to get correct
and a user-space API to think about.

Areas: Networking, Kernel

Estimated difficulty: 5/10


## Echo daemon in brainfuck

Implement a program that daemonizes itself, listens on a socket and echoes all incoming writes.
Use http://github.com/lava/amd64-bf as programming language.

Areas: Systems Programming, Brainfuck

Estimated difficulty: 11/10

Estimated difficulty when implementing a custom toolchain instead of writing "raw" brainfuck: 8.5/10 (estimated)

## Parse tree manipulation extension for C++

Extend gcc/clang to allow inline-lisp for manipulating the AST.

Areas: Compilers

Estimated difficulty: 9/10

## Cleansed tree

Implement a Gomory-Hu tree. Use https://github.com/munificent/vigil as programming language. 

Areas: Data Structures

Estimated difficulty: 6/10

## Vigilant C/C++

Create a version of vigil that handles C/C++ source files. Bonus points if sinful functions can also be removed from compiled libraries, to protect users from their harmful effects.

Areas: ABI, Linker

Estimated difficulty: 4/10
