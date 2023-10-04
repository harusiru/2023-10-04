# CLI(Command Line Interface) note
---
##### ***How to run Windows Linux***
1. Access the [git](https://git-scm.com/download/win) site
2. Download the git by choosing the right one out of 32 bits and 64 bits.
3. After installation, search for Gitbash in the Windows search box and run it.

---
### Standard Output

The standard output is the output stream produced when the program runs, which basically outputs results on the screen.
*-commands-*
">" - If you use the ">" you can send the standard output to a file rather than a screen. Use the ">" at this time. For example, the following command executes the ls command to store a list of files in the current directory in the 'files.txt file'.
"cat" - "cat" command is a command that outputs the contents of a file on the screen. For example, 'cat filename.txt' displays the contents of the 'filename.txt' file on the terminal.
">>" - >> is used to add output to a file. That is, add results to a file that already exists, or create a new file to record the results if the file does not exist.
ex) 'command1>>output.txt': Adds the execution result of 'command1' to the file 'output.txt'. If the file 'output.txt' does not exist, it is newly created. Add content if the file already exists.
---
### Standard Input
Standard Input is the default, and programs running on the terminal receive your keyboard input as standard input as standard input. This is typically used to read text from a terminal.
*-commands-*
"<" - You can use the "<" to redirect the input from the file. It sets the program to use the contents of the file as standard input.
and You can combine "<" and ">" to process inputs and outputs simultaneously.
ex)
```
&myprogram < input.txt > output.txt
```
This command uses the file "input.txt" as standard input while running "myprogram" and stores the output in the file "output.txt".

---
### Pipelines "|"
'|' is used to connect multiple commands to process or convert data. "|" uses to create pipelines and is responsible for forwarding the output of one command to the input of the next.
The pipeline simplifies complex tasks by combining multiple commands, and delivers intermediate results directly to the next command without saving them.
ex)
```
&command1 | command2
```
In this case, the output of 'command1' is passed through the pipeline to the input of 'command2'. You can calculate what 'command1' is and pass the results to 'command2' for further processing or filtering.

---
### Expansion
"\*"- The wildcard character "\*" is used to indicate the name of a matching file or directory. This character is useful for selecting or retrieving multiple files based on a pattern.
ex)
-*'.txt': Indicates all files in the current directory with the extension ".txt".
-'file*': Indicates all files and directories that begin with "file".
-'dir\*/subdir\*': Indicates all directories beginning with "dir" and beginning with "subdir".

"~" - The wave mark (~) is used to indicate the current user's home directory. This makes it easy to refer to the path of your home directory.
For example, ~ extends to the current user's home directory path. For example, it could be a path such as "/home/user" or "/Users/user".
Use '~username' to refer to the home directory of a particular user. For example, '~john' refers to the home directory of the "john" user.

---
### Tip:Backslash
Line Continuation - Backslash allows you to create long commands across multiple lines. This makes commands easier to read.
ex)
```
$ls -1 \
reverse
human-readable
```

---
### Permissions
File and directory permissions for Linux can be represented using the following symbols and notation:
- r (Read): Read permission. Files can be read.
- w (Write): Write permission. You can write to a file.
- x (Execute): Execution rights. Files can be executed.
- (Hyphen): No permission.
Permissions appear in the following format: rwxr-xr--

This permission string is divided into three groups:

Owner: Permissions assigned to the user who created the file or directory.
Group: Permissions assigned to the group of users who created the file or directory.
Others: Permissions assigned to all other users.
For example, rw-r--r-- means:
- Owner has read and write permissions.
- Group has read permission only.
- Other users only have read permission.
You can change these permissions using the chmod command, and you can use the ls -l command to verify the permissions in files and directories. Rights management plays a critical role in controlling access to files and directories, maintaining system security, and managing data sharing among users.

-*command "chmod"*-
1. The chmod command is used to change permissions in files and directories, and to change permissions, specify a number that represents permissions. Numbers are represented in octal form and use binary numbers to represent permissions. The number of permissions is shown as follows:

4: Read
2: Write
1: Execute
0: No Permission
Numbers representing permissions for each permission group (Owner, Group, Others) are arranged in the following order:

Owner 
Group 
Others (Other users)
For example, "6=110=rw-owner" is interpreted as follows:

Owner (owner): read (4) + write (2) = 6
Group: No permissions (0)
Others: No permission (0)
Therefore, "6" indicates that the owner is granted read and write permissions.

Similarly, "0=000=---forgroup" and "0=000=---forothers" indicate that they have no privileges for the group and other users, respectively.

Also, when you change file permissions using the chmod command, you can use these number of permissions to set or remove the desired permissions
![](https://i.ibb.co/WkZp9Pc/2002.png)
2. You can use the chmod command to change the permissions of the file "word.txt" so that only the owner (you) can read and write, and group and other users can read only. You can set permissions using numeric codes to indicate the permissions you want.
In this case, you can use the chmod command to set the following privileges:

Owner (owner): read (4) + write (2) = 6
Group: Read (4)
Others: Read (4)
```
$chmod 644 word.txt
```
---
### Superuser
- A superuser has all system administation authority
- Some commands need superuser’s privilleges.
- Put “sudo” before the command if you are a superuser
- Type “exit” to get out of a superuser session
![](https://i.ibb.co/brmRYqP/2003.png)

---
### TextEditors
- Vim: Vim provides a powerful command mode and supports a variety of plug-ins and extensions. Although the learning curve is rather steep, it provides excellent productivity for experienced users.
- Emacs: Emacs is a text editor that is highly scalable and offers a variety of features. Emacs is easy to customize and allows you to do many things through different modes and packages.
- Nano: Nano is a relatively simple CLI text editor, useful for beginners. Intuitive and easy to use.
- Gedit: Gedit is a text editor built into the GNOME desktop environment that provides a simple, intuitive interface.
- Kwrite: Kwrite is a lightweight text editor, primarily offered as the default text editing tool in KDE desktop environments.

---
### ShellScript
- Write and run a shell script
![](https://i.ibb.co/pvFnyyT/2004.png)

---
### Tip:History
The "history" command is used to display a list of commands previously entered by the user on Linux and Unix-based systems. This command allows you to check the command history and re-run or retrieve previously used commands.
