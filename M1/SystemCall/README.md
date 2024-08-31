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





