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

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |