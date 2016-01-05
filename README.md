# Programming challenges

Random ideas for projects. Feel free to submit pull requests adding more, the only requirement is being neither useful nor realistic ;) Please let me know if you manage to do one of these and I'll add a link to your source.

## Implement RFC5841 - TCP option to denote packet mood

Embedding the mood itself should be easy enough, but there are a lot of details to get correct
and a user-space API to think about.

Areas: Networking, Kernel

Estimated difficulty: 5/10

## Native linker and interpreter for brainfuck

Create a brainfuck linker that generates valid ELF executables.

Areas: Linking, ABI

Solutions:
  * http://github.com/lava/amd64-bf : Difficulty 3/10. Author's comment: Creating the ELF is relatively straightforward, and interpreting brainfuck is trivial. The trickiest part is to write the startup code for the interpreter in assembler, which requires learning a bit about relocations and the libc bootstrapping if you never did this stuff.

## Echo daemon in brainfuck

Implement a program that daemonizes itself, listens on a socket and echoes all incoming writes.
Use http://github.com/lava/amd64-bf as programming language.

Areas: Systems Programming, Brainfuck

Estimated difficulty: 11/10

Estimated difficulty when implementing a custom toolchain instead of writing "raw" brainfuck: 8.5/10

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

## Reversed function calls

Create a programming language where functions can only take one argument, but return an arbitrary number of arguments. Then implement some well-known recursive algorithms in that language.

Areas: Compilers, ABI

Estimated difficulty: 5/10 - 10/10, depending on how many other features the programming language will have and the choice of algorithms.
