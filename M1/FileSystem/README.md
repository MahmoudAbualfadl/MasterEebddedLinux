# Task

# Exercise 1: Basic Navigation
 - Use `ls` to list files and directors in the current directory.
 - Use `cd` to naviagete to a specific directory.
 - Use `pwd` to print the current working directory.

**OutputScreen And Commmands**
```
ls
cd github_x
pwd
```

<div>
  <img src="https://github.com/user-attachments/assets/e5a59007-88f8-4ca2-8b2c-0b6b31f47472">
</div>

# Exrcise 2: File and directory Operations
- Create a directory named "practice" in the current directory using `mkdir`.
- Create an empty file named "file.txt" within the "practice" directory using `touch`.
- Copy "file.txt" to new file "file_backup.txt" using `cp`.
- Move "file_backup.txt" to another directory using `mv`.
- Rename "file.txt" to "new_file.txt"using `mv`.
- Delete the "new_file.txt" using `rm`.

```
  mkdir pratice
  cd ./practice
  touch file.txt
  cp file.txt file_backup.txt
  mv file_backup.txt /home/github_x
  mv file.txt new_file.txt
  rm new_file.txt or rm -r new_file.txt
```

**OutputScreen And Commands**

<div>
<img src="https://github.com/user-attachments/assets/629df20d-e350-4a5e-819f-3caa661e1048">
</div>

# Exercise 3: File Viewing And Editing
- Create a text file using `echo` or a text editor like `nano`.
- View the content of file using cat.
- View the content of the file using less.
- Edit the file using `nano` or another text editor.
- Redirect the output of a command (e.g., ls) to a file using.

  ```
  echo "Mahmoud Will be working in big company insallah"
  echo "Mahmoud Will be working in big company insallah" >>file.txt
  cat file.txt
  less file.txt
  ```
  <div>
   <img src="https://github.com/user-attachments/assets/c2b36223-c3cb-4daf-8e4c-95ef004e6c7e">
  </div>

  ```
  nano file.txt
  cat file.txt > output.txt
  cat output.txt
  ```

  <div>
   <img src="https://github.com/user-attachments/assets/bf5f2364-971c-4b70-a265-ee57b19fcd5b">
  </div>

  # Exercise 4: File permissions
  
  - Create a file and set specific permissions using `chmod`.
  - Checking the permissions of the file using `ls-l`.
  - Change the owner and group of the file using `chown`
  - Verify the changes using `ls-l`.

    ```
    ls
    ls -l
    chmod 51 file.txt
    cat /etc/passwd
    cat /etc/group
    sudo chown mahhmoud file.txt
    ```
  <div>
   <img src="https://github.com/user-attachments/assets/c7021999-b946-47e3-8225-974fe2e4e9fe">
  </div>


 <div>
   <img src="https://github.com/user-attachments/assets/49433b3b-1382-424d-bb98-01a58d6f8000">
  </div>
  
# Exrecise 5 :User and Group Management

- Create a new user `useradd`.
- Set a password For the user using `passwd.`
- Create a new group using `groupadd`.
- Add the user to the newly created group using `usermod`.

  ```
  sudo adduser 
  sudo grouppadd
  sudo usermod -G 
  cat /etc/group
  ```
 
 <div>
   <img src="https://github.com/user-attachments/assets/27c5adda-19ac-4c49-a7e5-c7ae642b729c">
  </div>


  
   <div>
   <img src="https://github.com/user-attachments/assets/b76fe4be-b338-4787-b366-ce1826eca67a">
  </div>

  # Exrecise 6: Process Management
  - List all processes using `ps`.
  - List processes in real-time using `top`.
  - Find a specific process using `pgrep`.
  - Terminate a process using `kill`.

     <div>
   <img src="https://github.com/user-attachments/assets/e95ee307-3dfa-4a16-bf2b-b14add927921">
  </div>
  

   <div>
   <img src="https://github.com/user-attachments/assets/584e4590-54ee-40b2-8855-f3722f4cf593">
  </div>

  # Exrecise 7: File Searchimg
  
  **In this exercise, we will use the `find` and `grep` commands to search for specific files and        strings within files.**

  ## Commands Used to Solve Exercise 7
 
1. list files in the current directory:

`ls`

3. View the cintents of the files `output.txt`:
 
`cat output.txt`

3.search for a file named `output.txt` that contains the word "mahmoud" and print its path:

 `find . -name output.txt -exec grep -l Hello {} \;`

4.Search for the string "work" in the file output.txt:

`grep work output.txt`  



<div>
   <img src="https://github.com/user-attachments/assets/41972619-9e28-4c7c-9514-20a0e1f5227b">
  </div>

  # Exercise 9: Networking

   1. Ping spotify.com to test network connectivity:

    `ping spotify.com`
  
  2.Check network interfaces and their configurations:

    ` ifconfig`
  
  3.List all open ports:
   
   `netstat -tulpn`



<div>
   <img src="https://github.com/user-attachments/assets/fd05af62-3ea4-4ca4-8160-627b020fde0e">
  </div>

  

  
<div>
   <img src="https://github.com/user-attachments/assets/d8e5c7d3-a496-4b65-95af-058394e9273d">
  </div>

  
<div>
   <img src="https://github.com/user-attachments/assets/8f264ad2-603c-4271-9c09-84e73299afab">
  </div>

  # Exercise 10 :Package Mangement
   
   1-Update the package list using the package manager
    
    `sudo apt update`

    
   <div>
   <img src="https://github.com/user-attachments/assets/db1eff38-2fae-4857-b859-5808b6e15784">
   </div>
    
   

  
  
 
  
    
  


  
