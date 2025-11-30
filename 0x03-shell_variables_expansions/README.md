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

### Notes

- This task is purely educational, showing how aliases can override existing commands.
- Never use this alias in production or on important directories.
