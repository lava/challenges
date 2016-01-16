# Programming challenges

Random ideas for projects. Feel free to submit pull requests adding more, the only requirement is being neither useful nor realistic ;) Please let me know if you manage to do one of these and I'll add a link to your source.

## FizzBuzz in GNU make

    n = 100

    ten-times = $(1) $(1) $(1) $(1) $(1) $(1) $(1) $(1) $(1) $(1)
    
    stretch = $(subst 1,1 ,$(subst 2,2 ,$(subst 3,3 ,$(subst 4,4 ,\
              $(subst 5,5 ,$(subst 6,6 ,$(subst 7,7 ,$(subst 8,8 ,\
              $(subst 9,9 ,$(subst 0,0 ,$(1)))))))))))

    convert-digit = \
      $(subst 0,,\
      $(subst 1,_,\
      $(subst 2,_ _,\
      $(subst 3,_ _ _,\
      $(subst 4,_ _ _ _,\
      $(subst 5,_ _ _ _ _,\
      $(subst 6,_ _ _ _ _ _,\
      $(subst 7,_ _ _ _ _ _ _,\
      $(subst 8,_ _ _ _ _ _ _ _,\
      $(subst 9,_ _ _ _ _ _ _ _ _,$(1)))))))))))
     
    to-unary = $(if $(word 1,$(2)),\
         $(call to-unary,\
           $(call ten-times,$(1)) $(call convert-digit,$(word 1,$(2))),\
           $(wordlist 2,$(words $(2)),$(2))),\
         $(1))

    blanks := $(strip $(call to-unary,,$(call stretch,$(n))))
    
    acc = 
    seq := $(foreach x,$(blanks),$(or $(eval acc += z),$(words $(acc))))
    
    pattern = $(patsubst %5,Buzz, $(patsubst 3%,Fizz, $(patsubst 35,FizzBuzz,\
              $(join $(subst _ _ _,1 2 3,$(blanks)), $(subst _ _ _ _ _,1 2 3 4 5,$(blanks))))))

    fizzbuzz:
        @echo -e $(foreach num,$(seq),\
	         $(if $(findstring zz,$(word $(num),$(pattern))),\
	             $(word $(num),$(pattern)),\
	             $(word $(num),$(seq)))\\n)

Difficulty: 2/10. Authors comment: Bonus points if someone can generate `ten-times` and `stretch` with a foreach loop. 

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

## Fractional arrays

Compose a proposal to include fractional arrays into the ISO C++ standard.

    int arr[3.5]; // accessing the upper 16 bits of arr[3] results in undefined behaviour
    std::fill(arr[1.3], arr[1.6], 1); // set the middle bits of arr[1] to 1
    
Do not actually propose this to the committee. Bonus points for a sample implementation.

Estimated difficulty: 5/10

Areas: Technical Writing, ABI
