# Lab Report 5


```
# Create your grading script here

# set -e

rm -rf student-submission
git clone $1 student-submission
cd student-submission

if [[ -f ListExamples.java ]]
then
    echo "Found file with -f!"
else
    exit N
fi

if [[ -e ListExamples.java ]]
then
    echo "Found file with -e!"
else
    exit N
fi

javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java
java -cp ".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamples

echo $?
```
## Lab 3:

![Image](pictures\labReport5\listmeathodslab3.PNG)


## Corrected:

![Image](pictures\labReport5\lsitmeathodscorrected.PNG)


## Compile Error:

![Image](pictures\labReport5\listmeathodcompileerror.PNG)

1. For the line with the command `rm -rf student-submission`:
    - There is no standard output as it just removes the folder named student-submission and its contents.
    - There is no standard error as there is always a file named student-submission to remove.
    - Since the command succeded, the return code would be 0.

2. For the line with the command `git clone $1 student-submission`:
    - At first I thought the standard output would be the output of the git clone "Cloning into 'student-submission'". But when I used `>out.txt` to see the standard output, there was none, so this line does not contain any standart output.
    - There is no standard error since the repository always exists and manages to get cloned.
    - Since the command succeded, the return code would be 0
    
3. For the line with the command `cd student-submission`:
    - There is no standard output as it just changes its working directory into student-submission
    - There is no standard error as there is always a file named student-submission to change into
    - Since the command succeded, the return code would be 0
    
4. For the line with the first if statment with `[[ -f ListExamples.java ]]` as a condition:
    - There is no standard output as it just removes the folder named student-submission and its contents
    - There is no standard error as there is always a file named student-submission to remove
    - Since the command succeded, the return code would be 0
    
5. For the line with the first if statment with `[[ -e ListExamples.java ]]` as a condition:
    - There is no standard output as it just removes the folder named student-submission and its contents
    - There is no standard error as there is always a file named student-submission to remove
    - Since the command succeded, the return code would be 0
    
6. For the line with the command `javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java`:
    - There is no standard output as it just removes the folder named student-submission and its contents
    - There is no standard error as there is always a file named student-submission to remove
    - Since the command succeded, the return code would be 0
    
7. For the line with the command `java -cp ".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamples`:
    - There is no standard output as it just removes the folder named student-submission and its contents
    - There is no standard error as there is always a file named student-submission to remove
    - Since the command succeded, the return code would be 0
    
8. For the line with the command `echo $?`:
    - There is no standard output as it just removes the folder named student-submission and its contents
    - There is no standard error as there is always a file named student-submission to remove
    - Since the command succeded, the return code would be 0
    

| Line # | Standard Output | Standard Error | Return Code |
| ----------- | ----------- | ----------- | ----------- |
| Header | Title | Title | Title |
| Paragraph | Text | Text | Text |