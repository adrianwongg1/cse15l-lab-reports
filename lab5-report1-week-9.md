# Autograder Script
## Adrian Wong

**Writing a Grade Script**

My `grade.sh`:

```
CP=".:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar"

echo "cloning..."
rm -rf student-submission
git clone $1 student-submission

echo "sucessfully cloned"

cd student-submission

if [[ -e ListExamples.java ]]
then
    echo 'ListExamples.java was found! +1 pts'
else
    echo 'File not found, check file name. +0 pts'
    echo 'Some tests failed.'
    echo 'Total: 0 pts'
    exit 1
fi

cd ..
cp TestListExamples.java ./student-submission
cd student-submission

javac -cp $CP *.java 2> output-error.txt

file="output-error.txt"
if [[ -s $file ]]
then
    echo "File Compile Error, check error message. +0 pts"
    echo "Some tests failed."
    echo "Total: 1 pts"
    exit 1
else
    echo 'Compile success! +1 pts'
fi

java -cp $CP org.junit.runner.JUnitCore TestListExamples > junit-output.txt

if [[ $? -eq 0 ]]
then
    echo 'JUnit passed! +1 pts'
    echo 'All tests passed!'
    echo 'Total: 3 pts'
else
    echo 'JUnit failed! Check JUnit output +0 pts'
    echo 'Some tests failed.'
    echo 'Total: 2 pts'
    exit 1
fi
echo $?

```

Test 1:

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-11-28%20at%2010.03.41%20AM.png?raw=true)


Test 2:

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-11-28%20at%2010.04.30%20AM.png?raw=true)

Test 3:

![Image](https://github.com/adrianwongg1/cse15l-lab-reports/blob/main/CSE15L%20pictures/Screenshot%202022-11-28%20at%2010.03.53%20AM.png?raw=true)


**Script Trace**

Using Test 1's example, grade.sh first starts with removing the directory student-submission. Then,
git clone gets called, where it takes in the argument of the URL after the `grade.sh` in the bash terminal.
Line 17 cd's into the folder student-submission, where the if statement command in line 19 runs. The standard output 
is empty because the if-statement command returns false. As such, the standard error text for my particular script
is **File not found, check file name. Some tests failed. Total: 0 pts.**. The return code is 1 because it has failed 
to run the command successfully and I had set the exit to return the code of 1. Every line after the exit command in 
line 26 does not execute, due to the early exit of the false evaluation of the if command in line 19. 

