mahmoud is good at different thing 
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
  <img stc="Screenshot from 2024-08-27 05-47-54](https://github.com/user-attachments/assets/122ccfa4-4eb4-49f6-95fb-53c156bea510">
</div>



