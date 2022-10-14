# Remote Access and File System Instructions
## Adrian Wong

**Installing VSCode**

1. You will want to download VSCode.
[Link to VSCode](https://code.visualstudio.com/)
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/VSCode%20Website.png)
(Make sure you download the software based on your operating software)

2. Run the installer and open VSCode Terminal at the top toolbar.
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/Terminal.PNG)

**Connecting Remotely**

3. In the newly opened terminal, you will Log into the remote desktop:
`ssh cs15lfa22@ieng6.ucsd.edu`
In between "22" and "@", you will put your two letter or digit code assigned to you.
You will find your unique 2 letter username by looking up your username here:
![Link](https://sdacs.ucsd.edu/~icc/index.php)

![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/ssh.PNG)

You will type in your password after.
Note- the terminal will not give any feedback on your inputs.

4. After logging in, the terminal should look like this.
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/sshLogin.PNG)


**Trying Commands**

1. First, a basic command is running `ls`
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/ls.png)

2. Second, running `ls -a`
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/ls-a.PNG)

3. Doing the `exit` command in the terminal will terminate all processes and log you out.
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/exit.png)

**Moving Files with scp**

1. To move a file with scp, drop the file onto your desktop.

2. Go into the Terminal and type in the following command.
`scp FILENAME.java cs15lfa22__@ieng6.ucsd.edu:~/`
![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/scp.PNG)

3. Then log back into ssh and use the `ls` command for it to pop up in the directory.

**Setting up SSH key**
**Authorizing Local Computer to Remote Computer**

1. In the terminal, type `ssh-keygen`
2. When it asks to "Enter file in which to save key", just press enter.
3. When it asks to enter a passphrase, just keep pressing enter.
- You do not want to put anything here, as it defeats the purpose of allowing passkey-less entry.

![Image](https://adrianwongg1.github.io/cse15l-lab-reports/CSE15L%20pictures/sshKeygen.png)

4. Re-log back into the Remote Desktop and type in `mkdir .ssh`
5. Type in the terminal `scp /Users/<user-name>/.ssh/id_rsa.pub cs15lfa22__@ieng6.ucsd.edu:~/.ssh/authorized_keys`
Note - again, replace the two spaces with your unique 2 letter or digit code

6. Now, logging into ssh will save much time because you don't have to reinput your password everytime.

**Optimizing Remote Running**
Now that you have sucessfully enabled ssh login, you can make remote running more efficient.

1. Start by typing in the following command.
`ssh cs15lfa22__@ieng6.ucsd.edu "ls"`

This will allow you to run the command directly on the server,
and will list the home directory on the remote server.

2. You are able to also run simultaneous commands by separating the 
commands with a semicolon.
For example:
`cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

Note: Using the up arrow allows you to recall the previous commands that was run.




