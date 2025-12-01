# 0x03 – Shell, init files, variables and expansions

## Task 0: Alias

### Description

This project demonstrates how to create a shell script that defines an alias.  
The alias replaces the `ls` command with `rm *`, meaning that whenever you type `ls`, it will delete all files in the current directory.

⚠️ **Warning**: This alias is destructive. Running `ls` after sourcing the script will remove all files in the current directory. Use only in controlled environments for testing purposes.

### Script

File: `0-alias`

```bash
#!/bin/bash
alias ls='rm *'
```

### Usage

1. Create the script file:

   ```bash
   echo "alias ls='rm *'" > 0-alias
   chmod +x 0-alias
   ```

2. Source the script:

   ```bash
   source ./0-alias
   ```

3. Run `ls`:

   ```bash
   ls
   ```

   → This will delete all files in the current directory.
4. To bypass the alias and run the real `ls`:

   ```bash
   \ls
   ```

### Example

```bash
julien@ubuntu:/tmp/0x03$ ls
0-alias  file1  file2
julien@ubuntu:/tmp/0x03$ source ./0-alias
julien@ubuntu:/tmp/0x03$ ls
julien@ubuntu:/tmp/0x03$ \ls
0-alias
```

## Task 1: Hello you

**File:** `1-hello_you`

### Task 1: Description

Script that prints `hello user`, where `user` is the current Linux user.

### Task 1: Example

```bash
$ ./1-hello_you
hello julien
```

## Task 2: The path to success is to take massive, determined action

**File:** `2-path`

### Task 2: Description

Script that adds `/action` to the `PATH`.  
`/action` becomes the last directory the shell searches when looking for a program.

### Task 2: Example

```bash
$ source ./2-path
$ echo $PATH
...:/action
```

## Task 3: If the path be beautiful, let us not ask where it leads

**File:** `3-paths`

### Task 3: Description

Script that counts the number of directories in the `PATH`.

### Task 3: Example

```bash
$ . ./3-paths
11
```

## Task 4: Global variables

**File:** `4-global_variables`

### Task 4: Description

Script that lists all environment variables.

### Task 4: Example

```bash
$ source ./4-global_variables
HOME=/home/julien
PATH=/usr/local/bin:/usr/bin:/bin
LOGNAME=julien
...
```

---

## Task 6: Local variable

**File:** `6-create_local_variable`

### Task 6: Description

Script that creates a new local variable named `BEST` with the value `School`.

### Task 6: Example

```bash
$ source ./6-create_local_variable
$ echo $BEST
School
```

## Task 7: Global variable

**File:** `7-create_global_variable`

### ask 7: Description

Script that creates a new global variable named `BEST` with the value `School`.

### ask 7: Example

```bash
$ source ./7-create_global_variable
$ echo $BEST
School
$ env | grep BEST
BEST=School
```

## Task 8: Every addition to true knowledge is an addition to human power

**File:** `8-true_knowledge`

### Task 8: Description

Script that prints the result of adding 128 to the value stored in the environment variable `TRUEKNOWLEDGE`.

### Task 8: Example

```bash
$ export TRUEKNOWLEDGE=1209
$ ./8-true_knowledge
1337
```

## Task 9: Divide and rule

**File:** `9-divide_and_rule`

### Task 9: Description

Script that prints the result of dividing the value stored in the environment variable `POWER` by the value stored in the environment variable `DIVIDE`.

### Task 9: Example

```bash
$ export POWER=42784
$ export DIVIDE=32
$ ./9-divide_and_rule
1337
```

## Task 11: There are 10 types of people in the world

**File:** `11-binary_to_decimal`

### Task 11: Description

Script that converts a number from base 2 to base 10.  
The number in base 2 is stored in the environment variable `BINARY`.

### Task 11: Example

```bash
$ export BINARY=10100111001
$ ./11-binary_to_decimal
1337
```

## Task 12: Combination

**File:** `12-combinations`

### Task 12: Description

Script that prints all possible combinations of two lowercase letters, except `oo`.  
One combination per line, alpha ordered, starting with `aa`.

### Task 12: Example

```bash
$ ./12-combinations | wc -l
675
$ ./12-combinations | tail -303 | head -10
oi
oj
ok
ol
om
on
op
oq
or
os
```

## Task 13: Floats

**File:** `13-print_float`

### Task 13: Description

Script that prints the value stored in the environment variable `NUM` with two decimal places.

### Task 13: Example

```bash
$ export NUM=0
$ ./13-print_float
0.00

$ export NUM=98
$ ./13-print_float
98.00

$ export NUM=3.14159265359
$ ./13-print_float
3.14
```

## Task 14: Decimal to Hexadecimal

**File:** `100-decimal_to_hexadecimal`

### Task 14: Description

Script that converts a number from base 10 to base 16.  
The number in base 10 is stored in the environment variable `DECIMAL`.

### Task 14: Example

```bash
$ export DECIMAL=16
$ ./100-decimal_to_hexadecimal
10

$ export DECIMAL=1337
$ ./100-decimal_to_hexadecimal
539

$ export DECIMAL=15
$ ./100-decimal_to_hexadecimal
f
```

## Task 15: Everyone is a proponent of strong encryption

**File:** `101-rot13`

### Task 15: Description

Script that encodes and decodes text using ROT13 encryption.  
Assumes ASCII input.

### Task 15: Example

```bash
$ cat quote
"Everyone is a proponent of strong encryption."
- Dorothy E. Denning

$ ./101-rot13 < quote
"Rirelbar vf n cebcbarag bs fgebat rapelcgvba."
- Qbebgul R. Qraavat
```

## Task 16: The eggs of the brood need to be an odd number

**File:** `102-odd`

### Task 16: Description

Script that prints every other line from the input, starting with the first line.

### Task 16: Example

```bash
$ ls -1 | ./102-odd
bin
dev
home
lib
lib64
lost+found
mnt
proc
run
srv
t
t~
usr
vmlinuz
```

## Task 17: I'm an instant star. Just add water and stir.

**File:** `103-water_and_stir`

### Task 17: Description

Script that adds the two numbers stored in the environment variables `WATER` and `STIR`.  
- `WATER` is in base water.  
- `STIR` is in base stir.  
- The result is printed in base bestchol.

### Task 17: Example

```bash
$ export WATER="ewwatratewa"
$ export STIR="ti.itirtrtr"
$ ./103-water_and_stir
shtbeolhc
```

### Notes

- This task is purely educational, showing how aliases can override existing commands.
- Never use this alias in production or on important directories.
