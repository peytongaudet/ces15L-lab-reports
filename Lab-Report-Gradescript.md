# CSE 15L Lab Report Gradescript
## Peyton Gaudet (A17573280)

**Part 1: Testing on given repositories**

1. list-methods-lab3
![Image](LRgs1.1.png)

2. list-methods-corrected
![Image](LRgs1.2.png)


3. list-methods-compile-error
![Image](LRgs1.3.png)

**Part 2: Tracing the Script**

My grade.sh script:
```
# Create your grading script here

set -e

rm -rf combine
rm -rf student-submission
git clone $1 student-submission > dontneed.txt 2> dontneed2.txt

echo "If you see (FAIL), please fix the error and resubmit. 4 (PASS) notifications are requried for credit."
echo ""
echo ""

#2
cd student-submission
if [[ -e "ListExamples.java" ]]
then
    echo "ListExamples.java found. (PASS)"
else 
    echo "ListExamples.java not found. (FAIL)"
    exit 1
fi

#3
cd ..
mkdir combine

cd student-submission
cp ListExamples.java /Users/peyton/Documents/GitHub/list-examples-grader/combine/

cd ..
cp TestListExamples.java /Users/peyton/Documents/GitHub/list-examples-grader/combine/

rm /Users/peyton/Documents/GitHub/list-examples-grader/student-submission/ListExamples.java

#4
cd combine

set +e
javac ListExamples.java 2> compileLE.txt
if [[ $? -eq 0 ]]
then
    echo "ListExamples.java compiled successfully. (PASS)"
else
    echo "ListExamples.java did not compile. (FAIL)"
    exit 1
fi


javac -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar TestListExamples.java 2> compileTLE.txt
if [[ $? -eq 0 ]]
then
    echo "TestListExamples.java compiled successfully. (PASS)"
    echo "Running Test Methods..."
    java -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > feedback.txt    
    grep "OK" feedback.txt > dontneed3.txt
    if [[ $? -eq 0 ]]
    then
        echo "Test methods were successful. (PASS)"
    else
        echo "One or more test methods failed. (FAIL)"
    fi
else
    echo "TestListExamples.java did not compile. (FAIL)"
    exit 1
fi
```
