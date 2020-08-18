# Sh3ll-Script

## Example

```bash


#!/usr/bin/env bash

NAME="John"
echo "Hello $NAME!"


```

## Variables

```bash


NAME="John"
echo $NAME
echo "$NAME"
echo "${NAME}!"


```


## String Quotes

```bash
NAME="John"
echo "Hi $NAME"  #=> Hi John
echo 'Hi $NAME'  #=> Hi $NAME

```

## Shell Execution

```bash
echo "I'm in $(pwd)"
echo "I'm in `pwd`"
# Same

```


## Conditional Execution

```bash
git commit && git push
git commit || echo "Commit failed"

```

## Functions

```bash
get_name() {
  echo "John"
}

echo "You are $(get_name)"

```

## Conditionals

```bash
if [[ -z "$string" ]]; then
  echo "String is empty"
elif [[ -n "$string" ]]; then
  echo "String is not empty"
fi

```

## Strict Mode

```bash
set -euo pipefail
IFS=$'\n\t'

```

## Brace expansion

```bash
echo {A,B}.js

{A,B} 	Same as A B
{A,B}.js 	Same as A.js B.js
{1..5} 	Same as 1 2 3 4 5
```


# #Parameter expansions

## Basics

```bash
name="John"
echo ${name}
echo ${name/J/j}    #=> "john" (substitution)
echo ${name:0:2}    #=> "Jo" (slicing)
echo ${name::2}     #=> "Jo" (slicing)
echo ${name::-1}    #=> "Joh" (slicing)
echo ${name:(-1)}   #=> "n" (slicing from right)
echo ${name:(-2):1} #=> "h" (slicing from right)
echo ${food:-Cake}  #=> $food or "Cake"

length=2
echo ${name:0:length}  #=> "Jo"

```


## Parameter Expansion

```bash
STR="/path/to/foo.cpp"
echo ${STR%.cpp}    # /path/to/foo
echo ${STR%.cpp}.o  # /path/to/foo.o
echo ${STR%/*}      # /path/to

echo ${STR##*.}     # cpp (extension)
echo ${STR##*/}     # foo.cpp (basepath)

echo ${STR#*/}      # path/to/foo.cpp
echo ${STR##*/}     # foo.cpp

echo ${STR/foo/bar} # /path/to/bar.cpp

STR="Hello world"
echo ${STR:6:5}   # "world"
echo ${STR: -5:5}  # "world"

SRC="/path/to/foo.cpp"
BASE=${SRC##*/}   #=> "foo.cpp" (basepath)
DIR=${SRC%$BASE}  #=> "/path/to/" (dirpath)

```


