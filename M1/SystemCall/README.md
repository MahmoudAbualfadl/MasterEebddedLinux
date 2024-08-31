# System Call 
## Task 1
### Trace System call for `ps` & `cd` & `ls`  commands
**Tracing system calls for the commands `ps`, `cd`, and `ls` involves understanding the underlying system calls that these commands make to interact with the operating system. I'll outline the basic system calls involved in these commands**
# System Calls for `ps` Command

The `ps` command is used to display information about active processes. The following system calls are typically involved when executing the `ps` command:

- **`fork()`**: Creates a new process if `ps` needs to run in a new process.
- **`execve()`**: Executes the `ps` command itself or a related program.
- **`waitpid()`**: Waits for the `ps` command to complete if it is a child process.
- **`getpid()`**: Retrieves the process ID of the current process.
- **`getppid()`**: Retrieves the parent process ID.
- **`read()`** and **`write()`**: Read and write process information to and from files or output.
- **`open()`** and **`close()`**: Open and close files that contain process information (e.g., `/proc` filesystem).
<div>
  <img src="https://github.com/user-attachments/assets/122ccfa4-4eb4-49f6-95fb-53c156bea510">
</div>

# `cd` Command
the `cd` (change directory ) commmand change current working directory of the shell:
 - **`chidr()`**: this is the primary system calll used by the `cd` command to change the current working directory
 - **`getcwd`**:often used by the shell to get current working directory before changing it .
 <div>
  <img src="https://github.com/user-attachments/assets/641f16f6-4ccd-411c-810f-d31a86b4ee32">
</div>

`ls` command 
the `ls` command lists directory content involves several system calls:
 - **`open()`**: to open directoery to read contents.
 - **`getdents()`**: To get directory entries (this is low -level system used to read directory contents).
 -  **`read()`**: to read directory entriesif the `getdents()` call is not used.
 -  **`close()`**: To close the diretory files descriptor after reading contents.
 -  **`stat()`** and **`lstat()`**: to get files status information (e.g., to check file types and permissions).
 - **`readsir`** to read directory entries in a more user-friendly way ( if implemented int the program).
  <div>
  <img src="https://github.com/user-attachments/assets/ca1682c3-9736-4333-afff-d61e55fd13f5">
</div>

# Tracing System Calls
## **To trace these system calls, you can use tools like strace on Linux. Here’s how you might use strace to trace these commands:**
```
strace ps
>For cd (note: cd is typically a shell built-in, so tracing it might require tracing the shell):
strace -e trace=chdir bash -c 'cd /path/to/directory'
strace ls
```
## Task2
## 1 .extract files of interactions.
# Extracting and Analyzing System Calls

To understand the interactions between commands and the operating system, you can use `strace` to capture the system calls made by commands. Below are the steps to extract and analyze these interactions for the `ps`, `cd`, and `ls` commands.

## 1. `ps` Command

To capture system calls made by the `ps` command, follow these steps:

1. **Run `strace` to Capture System Calls**:
    ```bash
    strace -o ps_trace.txt ps
    ```

    - `-o ps_trace.txt`: Directs `strace` to write the output to a file named `ps_trace.txt`.

2. **Analyze the Output**:
    - Open the `ps_trace.txt` file in a text editor or use a command like `less` or `cat` to view the captured system calls:
      ```bash
      less ps_trace.txt
      ```

    - Look for system calls like `fork()`, `execve()`, `waitpid()`, `getpid()`, `getppid()`, `read()`, `write()`, `open()`, and `close()`.

## 2. `cd` Command

To trace the `chdir` system call made by the `cd` command, follow these steps:

1. **Run `strace` to Capture the `chdir` System Call**:
    ```bash
    strace -e trace=chdir -o cd_trace.txt bash -c 'cd /path/to/directory'
    ```

    - `-e trace=chdir`: Filters the trace to include only `chdir` system calls.
    - `-o cd_trace.txt`: Directs `strace` to write the output to a file named `cd_trace.txt`.

2. **Analyze the Output**:
    - Open the `cd_trace.txt` file in a text editor or use a command like `less` or `cat` to view the captured system calls:
      ```bash
      less cd_trace.txt
      ```

    - Check for `chdir()` system calls to see how the directory change is performed.

## 3. `ls` Command

To capture system calls made by the `ls` command, follow these steps:

1. **Run `strace` to Capture System Calls**:
    ```bash
    strace -o ls_trace.txt ls
    ```

    - `-o ls_trace.txt`: Directs `strace` to write the output to a file named `ls_trace.txt`.

2. **Analyze the Output**:
    - Open the `ls_trace.txt` file in a text editor or use a command like `less` or `cat` to view the captured system calls:
      ```bash
      less ls_trace.txt
      ```

    - Look for system calls such as `open()`, `getdents()`, `read()`, `close()`, `stat()`, and `lstat()`.

## Summary

Using `strace` to capture and analyze system calls can help you understand how commands interact with the kernel and filesystem. By redirecting the output to files and examining these files, you can gain insights into the specific system calls made by each command.

Feel free to modify the file names and paths according to your needs.

# Identifying and Measuring System Calls

## Identifying System Calls

To identify all system calls used by a command, use `strace`:

1. **Capture System Calls**:
    ```bash
    strace -o trace_output.txt command
    ```

    Replace `command` with the command you want to trace (e.g., `ps`, `cd`, `ls`).

2. **Extract Unique System Calls**:
    ```bash
    grep -o '^[a-z_]*(' trace_output.txt | sort | uniq
    ```

    This will list all unique system calls made by the command.

3. **Manual Inspection**:
    Open `trace_output.txt` in a text editor for detailed analysis.

## Measuring System Calls Performance

To measure the performance of system calls:

1. **Measure Total Execution Time**:
    ```bash
    time strace -o trace_output.txt command
    ```

    This command will output the execution time along with the system call trace.

2. **Analyze Execution Time**:
    The `time` command provides the real, user, and system times, which indicate the total time taken for the command to execute.

3. **Measure Time for Specific System Calls**:

    Using `perf`:

    ```bash
    sudo perf trace -e syscalls --call-graph dwarf command
    ```

    This will show detailed timing information for each system call.

By following these steps, you can identify and measure the performance of system calls to understand their impact and behavior in different commands.







