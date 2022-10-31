# Researching Commands
## Adrian Wong

**Grep**

Grep takes in a string, followed by files to search in to find the coressponding lines containing the string.

1. Using the Skill-demo1 files, `grep "taxation" */*/*.txt` looks for files within technical 
to find files that contain the word "taxation" within. 

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.09.45%20PM.png?raw=true)

2. Using `grep -l "taxation" */*/*`, it searches through the 3rd subdirectory to find files
that have the word "taxation within. It printed out the following.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.16.34%20PM.png?raw=true)

3. Using `grep -n "taxation" */*/*/*`, it searches through the 4th subdirectory to find
the file name that contains taxation, as well as prints out the line within the file
that contains the string we are searching for.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.19.44%20PM.png?raw=true)


**less**

The less command displays a file in the terminal as output.

1. Using `less -N */*/chapter-1.txt`, the entire file of chapter-1.txt gets printed out in the terminal, with
each line being numbered on the left side.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.24.29%20PM.png?raw=true)

2. Using `less -X */*/chapter-1.txt`, the entire file of chapter-1.txt gets printed out in the terminal, but
after pressing Q to leave, the printed file stays in the terminal.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.27.33%20PM.png?raw=true)

3. Using `less -S */*/chapter-1.txt`, the long lines at the end of each line gets cut off, pointing to the next
line in the terminal. In addition, it adds empty lines in between each of the lines.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.32.22%20PM.png?raw=true)


**find**

The find command finds all the files/directories that are passed in and can preform different operations on
the passed in information.

1. Using `find ./technical -name chapter*`, it searched for file names within technical that contained
the word "chapter". It printed out each file name that contained that prefix.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.39.26%20PM.png?raw=true)

2. Using `find ./technical/911report -print`, it printed out every file path within /technical/911report,
even the directory path itself.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.42.17%20PM.png?raw=true)

3. Using `find ./technical -empty`, it searches through each file to find if there are any empty files. It
found one file that was empty, and printed out its path.

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-10-30%20at%2011.44.37%20PM.png?raw=true)

