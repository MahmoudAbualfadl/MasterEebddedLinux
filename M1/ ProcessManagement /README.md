# Process Management Stack. 
**This repository provides examples of how to check the number of CPU cores and manage processes using various commands.**
## TASK
**1. Check how many cores do you have using `top` command.**

To check how many CPU cores you have , you can use the `top` command.

- **Open**: Terminal.
- **Type**: `top` and press Enter.
- **Once**: `top` is runing , press `1` key to show a detailes view of each CPU core.
  ## Output Screenshot:
  <div>
   <img src="https://github.com/user-attachments/assets/e6924bb9-39fb-493f-874e-ff94aab16e87">
  </div>

  ## Analyizing
  
from `top` command output you provid it looks like you have 16 cpu cores available this is inferred from `cpu0` to `cpu15` lines in the output ,which each represent a different core
each line shows the usage statistics for one core from `cpu0` through `cpu15` indicating that there are 16 cores in total.

**2.Creating Processes in Background.**

in this example ,we will create a number of procsses to stress the system we will use the `dd`
command to create preocess in the background.

**Command Used:**

`sudo dd if=/dev/zero of=/dev/null &`

**3.Changing Priority for Processes**

To change The priority of processes , we can use the `renice` command. The priority
values range from -20 (highest priority) to 19 lowest priority .Higher negative
values indicate higer priority ,while postive values indcate lowe priority

**Command Used**
```
sudo renice -n -20 -p <process_id>
sudo renice -n -10 -p <process_id>
sudo renice -n 0 -p <process_id>
sudo renice -n 19 -p <process_id>
```

Replace `process_id` with the process IDs obtained from the `top` command or any other process management tool

**4.Killing Processes, We can Usse the `killall`
command followed by the precess name

**comand Used:**
```
killall -g top
