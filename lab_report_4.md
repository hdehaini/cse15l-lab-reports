# Lab Report 3


## Part 1
## Task: Changing the name of the `start` parameter and its uses to `base`

### Full Sequence:

`/start<enter>cgnbase<esc>n.<esc>n.<esc>n.<esc>:wq`

### Discription:

![Image](pictures\labReport4\searchForStart.JPG)

- This image shows me finding the first iteration of `start` by entering `/start` then `<enter>`.
- I then type in `c` `g` `n` to delete and change the word that I looked for and save the pattern that I replaced it with.
- In this case, I will replace it by typing the pattern: `base`

---

![Image](pictures\labReport4\changeSecondStart.JPG)

- After clicking `<esc>` to exit out of INSERT mode, I simply type in `n` and then `.` to replace the next iteration of the word I looked for, in this case `start`, with the previous saved pattern , in this case `base`.
- I then click `<esc>` to get out of INSERT mode to do this again for the other iterations.

---

![Image](pictures\labReport4\changeThirdStart.JPG)

- I once again type `n` and `.` to replace the orginal word with `base` and then `<esc>` to exit INSERT mode to do it one last time.

---

![Image](pictures\labReport4\changeLastStart.JPG)

- I type in `n` and `.` to change the last iteration of `start` with `base`, and press `<esc>` to exit INSERT mode.

---

![Image](pictures\labReport4\saveAndExit.JPG)

- I simply type in `:` `w` `q` and `<enter>` to save and exit the code.

---

## Part 2

SCP: It took me about **51 seconds** to edit the code in VS Code and scp it to the remote server.

SSH: It took me about **47 seconds** to edit the file through vim in an ssh login.

There are a few pros and cons to both methods. For SCPing the file, it was really easy to edit the file in VS Code because I know that if I highlight a word and `CTRL d`, I can edit all the iterations at the same time. However, what took the longest was typing the SCP command out. Testing it was pretty straight forward.

SSHing the file then editing it in vim also wasn't bad. Understanding how to easily change multiple words at the same time in vim from this lab made it pretty quick. However, I didn't originally have the file on the remote server. So I had to put it there myself before testing it out

What I've come to realize is that the issue isn't with editing the file, even though editing in vim takes a bit longer than in VS Code, but the actual location of the file I want to edit.

- I would definetly perfer SCPing if I had the command to SCP at the ready, instead of typing the whole line out. However, if I had the file already at the remote server without me having to put it there and I don't have the SCP command at the ready, I would rather SSH.

- Knowing where the file I need to change is is definetly the biggest factor to when I would do either method.