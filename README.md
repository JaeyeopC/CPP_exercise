**CIIP C++ Course**

## Operating System

We're cannot stress enough that your lecture experience using Windows will most likely be painful.
You should really consider installing Linux (e.g. [Ubuntu](https://ubuntu.com)) (also possible alongside Windows), or at least use Linux on Windows (the [WSL](https://learn.microsoft.com/en-us/windows/wsl/)).


## Compiler

As we'll be covering modern C++ (C++20) you need a recent compiler, otherwhise your project will not compile.

Recommended compilers are:
- GNU GCC 11 and higher (Linux: install `g++` with your package manager, [Windows](https://nuwen.net/mingw.html))
- LLVM Clang 13 and higher
- (Visual Studio 2022 17.0 and higher)

We will be testing with GCC 11 and Clang 13 on Linux.
It therefore could be possible that you encounter errors with other versions.


## Build system (CMake)

For later assignments we use the [CMake](https://cmake.org/) build system.
It takes care of building/compiling everything in the right order and hooking everything up, rather than forcing us to manually manage (and possibly forget) some elements or links.
Follow [this tutorial](https://cmake.org/install/) to install CMake.


## IDE

You can use any text editor you are comfortable with.
We use [Doom](https://github.com/doomemacs/doomemacs) [Emacs](https://www.gnu.org/software/emacs/), [Spacemacs](https://www.spacemacs.org/) (both unify the advantages of Vim and Emacs) and [vim](https://www.vim.org/)/[neovim](https://neovim.io/).
If you don't have any preference yet, we recommend [CLion](https://www.jetbrains.com/community/education/#students) or [VSCode](https://code.visualstudio.com/).


# Troubleshooting



## Unexpected Contents


To ensure the tests are unmodified for grading, we check if the file content hashes are correct.

During the CI run, we validate that `/CMakeLists.txt` and the `tests/` directory are as expected, but we can't pre-check `/.gitlab-ci.yml` without breaking the universe.

Do not modify these files - otherwise your homework can't be graded!

If you do modify them and get an error message, you must not fix your code by rewriting git repo history (using `git force-push`) - you can only ever add new things to your repo history, not delete old history elements.


### Fixing Unexpected Contents


You can always make sure the files are in the "correct" state by running:

```bash
# if you want, inspect what you've changed
git diff upstream/master..HEAD CMakeLists.txt tests/ .gitlab-ci.yml

# undo the changes
git restore -s upstream/master CMakeLists.txt tests/ .gitlab-ci.yml

# and commit what is needed to undo your changes
git add CMakeLists.txt tests/ .gitlab-ci.yml
git commit -m "restore important files i should not have modified"
```
