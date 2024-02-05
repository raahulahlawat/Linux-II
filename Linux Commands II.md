# Linux-Assignment-4

### Ques 1: Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.

```
cd /home
```
```
ls
```
```
sudo mkdir MyFiles
```
```
ls
```
```
cd MyFiles
```
```
ls
```
## Output 
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/bc0cc748-1e8d-49ea-85fa-9d63e8059010)


### Ques 2: Copy a file named "file.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "file" within "MyFiles."

```
cd /home
```
```
ls
```
```
sudo touch file.txt
```
```
ls
```
```
sudo cp file.txt MyFiles/
```
```
cd MyFiles/
```
```
ls
```
```
sudo mkdir -p file
```
```
cd ..
```
```
sudo mv MyFiles/file.txt MyFiles/file

```
```
cd MyFiles
```
```
ls
```
```
cd file
```
```
ls
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/a78cc916-c329-493b-b8f7-e40679e92ad1)


### Ques 3 : Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.

```
cd /home/MyFiles/
```
```
ls
```
```
sudo touch notes.txt
```
```
ls
```
```
sudo rm -rf notes.txt
```
```
ls
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/af2d55a9-7ff3-424d-9430-594818435c37)


### Ques 4 : Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.

```
cd /home/MyFiles/Document
```
```
ls
```
```
sudo ln document.txt hardlink.txt
```
```
ls
```
```
ln -s document.txt symlink.txt
```
```
ls
```

### Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/5b8f98aa-0eba-4339-974e-bf6ad0ddf175)


### Ques 5 : In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.

```
cd /home/MyFiles/
```
```
ls
```
```
sudo touch a{1..10}.txt
```
```
sudo touch b{1..10}.txt
```
```
sudo touch c{1..10}.txt
```
```
ls
```
```
sudo ls /home/MyFiles/a*.txt
```

## Output

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/dd8924cf-2d61-4943-ba27-4d82187f3e78)


### Ques 6: Rename all files in the "file" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.

* If we do not have installed rename we have to install it first

```
sudo apt-get update
```
```
sudo apt-get install rename
```
```
cd /home/MyFiles/file
```
```
ls
```
```
sudo touch aa.txt bb.txt cc.txt dd.txt
```
```
ls
```
```
sudo rename -n 's/\.txt$/.bak/' *.txt
```
```
ls
```
```
sudo rename 's/\.txt$/.bak/' *.txt
```
```
ls
```

### Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/e4026884-c67e-492c-ab62-f2fe2098933c)



### Ques 7: Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup".

```
cd /home/MyFiles/
```
```
ls
```
```
sudo mkdir backup
```
```
ls
```
```
cd
```
```
sudo cp /home/MyFiles/file/* /home/MyFiles/backup/
```
```
cd /home/MyFiles/backup/
```
```
ls
```
```
cd ..
```
```
cd file/
```
```
ls
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/d19d7934-00b8-4713-96b4-c21cc0d6b40b)


### Ques 8 :Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.

```
cd /home/MyFiles/file/
```
```
ls
```
```
sudo mkdir b
```
```
sudo touch a.txt
```
```
ls
```
```
cd ..
```
```
ls
```
```
sudo touch file_list.txt
```
```
ls
```
```
cd file
```
```
chmod +rwx a.txt b
```
```
cd ..
```
```
chmod +rwx file_list.txt
```
```
cd file
```
```
ls > ../file_list.txt
```
```
cd ..
```
```
grep '\.txt$' file_list.txt
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/2606c4c0-34dd-4ba8-a6d2-cdd58b9569ff)


### Ques 9: Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.

```
cd /home/MyFiles/
```
```
sudo touch my_notes.txt
```
```
sudo vim my_notes.txt
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/b33f96b6-ccdd-4061-b010-2cd96cfb9dbd)

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/cfa42a44-16d5-4735-959c-9bdf2786fee1)


### Ques 10 :Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.

```
sudo -i
```
```
cd /home/MyFiles/
```
```
sudo current_date=$(date)
```
```
sudo echo "current date : $current_date"
```
```
sudo echo "$current_date" >> my_notes.txt
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/d207ab7e-71aa-4392-8044-c85b8fd53bf1)

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/b7e115bd-a6d0-4910-9ea5-66566dbd76dd)


<!-- ### Ques 11 : Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.

```
sudo -i
```
```
vim .bashrc
```
```
export CUSTOM_PATH="/home/MyFiles/Document"
```
```
source ~/.bashrc
```
```
echo $CUSTOM_PATH
``` -->

### Ques 12 : Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.

```
sudo -i
```
```
cd /home/MyFiles
```
```
echo "I am writing text in new line" >> my_notes.txt
```
```
cat my_notes.txt
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/dffc2cf0-dc91-4a03-8631-eebb16c76bbd)


### Ques 13 : List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."

```
ls /etc | grep 'conf' > conf_files.txt
```
```
vim conf_files.txt
```
```
cat conf_files.txt
```

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/abfa82e1-30a2-424c-aee3-8541d2581503)


### Ques 14 : Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.

```
cd /home/MyFiles
```
```
sudo vim my_notes.txt
```
* After opening file write below command after press shift + colon

```
%s/important/critical/g
```
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/915636ee-62ce-496b-a853-3554295bfa31)

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/73ef21c0-03a6-461b-b709-d6cbb4599342)

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/6793f642-323e-4a81-b2de-b43513dbc88b)


## Ques 15 : Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.

```
sudo useradd -m -d /home/john_doe -g users john_doe
```

## Output

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/2ed68443-d5ff-4a4e-9a68-0968e7ebbaec)



### Ques 16 : Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.

```
sudo visudo
```
* Inside visudo file write below content and save it and exit

```
john_doe   ALL=(ALL:ALL) NOPASSWD: ALL
```
* After save above command
```
sudo su - john_doe
```
```
sudo ls /root
```
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/74d4138d-b054-4822-8bb6-b484da16d57d)


### Ques 17 :Modify the user account "john_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.

```
sudo chsh -s /bin/bash john_doe
```
```
sudo chage -E $(date -d "+1 month" +"%Y-%m-%d") john_doe
```

### Ques 18 :Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.

```
sudo groupadd development_team
```
```
sudo usermod -aG development_team john_doe
```
```
getent group development_team
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/88118f4e-acda-4a16-9adb-8bbcfc0f523e)


### Ques 19 : Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.

```
sudo gpasswd -d john_doe users
```
```
sudo usermod -aG development_team john_doe
```
```
groups john_doe
```

## Output

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/d880ddcb-e0fb-4590-b1fa-f360bf886e38)



<!-- ### Ques 20 :Delete the user account "john_doe" and ensure that their home directory is also removed.

```
sudo userdel -r john_doe
```
```
groups jhon_doe
``` -->

### Ques 21 : Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.

```
getent group development_team
```
```
sudo groupdel development_team
```
```
getent group development_team
``` 
## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/7689515e-e75a-4dda-9202-5ea5dd093353)


### Ques 22 : Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.

```
sudo chage -M 90 -m 0 -W 7 -I 30 -E -1 $(cut -d: -f1 /etc/passwd)
```
```
sudo vim /etc/login.defs
```
* Inside this file add max pass day as 90 and min pass day as 0
```
PASS_MAX_DAYS   90
PASS_MIN_DAYS   0
```
## Output

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/8867a3dd-02cd-4dca-81e3-46066905d5f2)

![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/8760df66-e446-4c8a-ae90-30b2d70417f9)


### Ques 23 : Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.

```
sudo passwd -l john_doe
```
```
su - john_doe
```
```
sudo passwd -u john_doe
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/ecbbf674-6b5f-4bc4-859e-77001f71d32b)



### Ques 24 : Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.

```
id john_doe
```
```
id -u john_doe
```
```
id -g john_doe
```
```
id -G john_doe
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/81050d3d-0ede-4e17-8275-13d9a4a2d40d)



### Ques 25 : Configure the password aging for the user "john_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.
```
sudo chage -M 60 john_doe
```
```
sudo chage -l john_doe
```

## Output
![image](https://github.com/raahulahlawat/Linux-II/assets/151362887/3521b61e-eada-4a9a-9992-abc56139b141)
