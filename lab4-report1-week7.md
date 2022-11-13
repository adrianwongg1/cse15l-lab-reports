# Vim
## Adrian Wong

**Part 1**

My group came up witht he shortest sequence of `vim` commands when accomplishing the 
task of adding a new line to `print` before `File[] paths = f.listfiles();`

The command sequence is as follows:
`vim T<Tab><enter> /10<enter> L X I 391 <esc> :wq`

Step 1: vim into the file, in this case, it is TestDocSearch.java.

Step 2: Find the location to where you want to change the values. 
Here, I used `/10<enter>`
![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/forwardslash10.PNG?raw=true)

Step 3: Pressed `L` to move right, `X` to remove, `I` to begin inserting.
![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/pressedX.png?raw=true)

Step 4: Pressed `391` to add the value to where the cursor is.
![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/insert391.PNG?raw=true)

Step 5: Press <esc> to exit out of inserting, and `:wq` to write the code, and quit.
![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/pressedColwq.PNG?raw=true)


**Part 2**

Doing the exits in VSCode and then scp'ing the file into the remote server with the scp
command ready to go as well as ssh keys set up took me around 1 minute to do.

Making the edit in ssh and doing the tasks in Vim took me around 30 seconds to do so, not
considering the time it takes to git clone the file, as I am assuming that I am doing the
task as if the files were already good to go.

1. I prefer to work on VSCode simply because I have the freedom to move around the code or page
however I choose with a click of a mouse. The convenience of being able to text edit and save
code or files without pressing so many buttons I think saves more time in the long run.

2. I think if it was a large number of files and it takes up much computer power to run the 
commands and scripts, doing vim on remote would save a lot of computering power locally and 
could run the scripts or commands that might take a local computer much slower than a server
would.s

