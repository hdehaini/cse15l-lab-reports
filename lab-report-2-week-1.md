# **Week 1 Lab Report**
### *Hamza Dehaini*

---

## Installing VScode

1. Go to the [VSCode](https://code.visualstudio.com/)
2. Follow the instructions in the website to download and install the application based on your OS System (Windows or MAC OS)
3. After you are done installing VSCode, open the program, and you should come to a get started page similar to this:

![Image](pictures\installingvscode15l.JPG)

---

## Remotely Connecting

1. You will need to install the SSH client if you don't already have it
- For Windows users, to double check that you have the SSH client installed, you can open powershell on your machine and enter:

```
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
```

- If you have it installed, you will get an output of:

![Image](pictures\psoutput.JPG)

2. To connect to the remote computer, you will need to open the VSCode terminal
- Typing Ctrl or Command `
- Or select Terminal -> New Terminal on the top of your VSCode menu bar
3. Enter the SSH command in the VSCode terminal:

```
ssh cs15lfa22zz@ieng6.ucsd.edu
```

- replace `cs15lfa22zz` with your username from your course

4. Select yes to the following prompt:

```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

5. Type in your password. WARNING: There is no visual output when you are typing your password. Continue to type and enter your password and it is still being inputed, even if you can't see it.

6. It will then output and prompt of security warnings as you are now controlling the remote computer

![Image](pictures\remote.JPG)

- Shows automatic output from the admins when "SSHing" and displays the status of the remote computers

---

## Trying Some Commands

1. To test out the remote computer, you can try some commands

![Image](pictures\commands.JPG)

- This image test these commands in order:

  - `ls`
  - `cd ~`
  - `-lat`
  - `cat /home/linux/ieng6/cs15lfa22/public/hello.txt`
  - `ls -a`

2. Logout by either pressing Ctrl-D, or running the command `exit` in the terminal

3. Run a few of the commands from step 1. Notice how the same commands are different. This is because you are looking at the files of your home computer, rather than the remote computer in step 1:

![Image](pictures\commands1.JPG)

- This image test these commands in order:

  - `ls`
  - `cd ~`

---

## Moving Files with SCP

1. To copy and paste files between computers using SCP, we will use a test file for this task. Add a file to your computer titled `WhereAmI.java` with this code:

```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

2. Run these two commands in the terminal
- This will make a class of WhereAmI.java, then run it. It should then output your OS, user, home, and directory name

```
javac WhereAmI.java
java WhereAmI
```

3. Run this command to copy and paste the files from the client machine to the remote machine (Swich out 'cs15lfa22zz' woth your username and retype your password)

```
scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/
```

- This image displays the steps from 2 - 3

![Image](pictures\scp.JPG)

1. Log back in with the ssh command again
2. Enter ls to the terminal to see all files in the current directory
3. Type in these two commands for the same opperation once again. Notice OS, user, home, and directory name is different since it is a different computer altogether

```
javac WhereAmI.java
java WhereAmI
```

- This image displays the steps from 2 - 3

![Image](pictures\ssh.JPG)

---

## Setting an SSH Key

1. To eliminate the need to continuously put in your password to swich computers and to copy files, we will use SSH keys
2. Enter `ssh-keygen` to the terminal, and press enter not add any passphrase. You will know it finished when there is a randomart image at the end
- This make a public and private key that saves to your client machine

![Image](pictures\settingssh.JPG)

3. Now, we need to copy the public key to the .ssh directory on the server
4. Enter this line with your information:

```
ssh cs15lfa22zz@ieng6.ucsd.edu
```

5. On the server computer, enter this line, then logout:

```
mkdir .ssh
```

6. Back on your your client computer, enter this line with your information

```
scp /Users/joe/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys
```

![Image](pictures\settingssh2.JPG)

---

## Optimizing Remote Running

- Now you can run SSH and SCP commands without having to put in your password
- Some more efficient trick you can use are directly putting a command in quotes for the remote server on your client computer without having to sign out. For Example:

```
ssh cs15lfa22@ieng6.ucsd.edu "ls"
```

- You can also use semicolons to run multiple commands at once:

```
cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```

- The image shows a few these and a few other commands you can try out!

![Image](pictures\quicktricks.JPG)

---

# Congrats! You're now an expert in SSH and SCP :)