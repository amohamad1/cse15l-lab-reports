# Lab Report 5: Grade Script

The follwing is the grading bash script: 

``` rm -rf student-submission
git clone $1 student-submission

if [[ $? -eq 0 ]]
then
    echo "Student repo found"
else
    echo "Student submission was not found. Ensure correct repo link"
    exit 1
fi

cp TestListExamples.java student-submission

cd student-submission


if [ -f "./ListExamples.java" ]
then
    echo "file exists"
else
    echo "file does not exist"
    exit 1
fi

javac -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar *.java

if ! [[ $? -eq 0 ]]
then
   echo "Test failed to compile error."
   exit
fi

java -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > result.txt

testResults=$(grep -i "Tests run:" result.txt)


if [[ $testResults == "" ]]
then
  echo "All tests passed. Good Job."
  echo "Grade: 100%"

else
  echo "tests failed"
  echo "Grade: 0%"
fi

exit 0 
```

Output to this repo: https://github.com/ucsd-cse15l-f22/list-methods-lab3:

![Image](https://amohamad1.github.io/cse15l-lab-reports/report5/screenshot1.png)

Out to this repo: https://github.com/ucsd-cse15l-f22/list-methods-corrected:

![Image](https://amohamad1.github.io/cse15l-lab-reports/report5/screenshot2.png)

Out to this repo: https://github.com/ucsd-cse15l-f22/list-examples-subtle:

![Image](https://amohamad1.github.io/cse15l-lab-reports/report5/screenshot3.png)


In the last example, the script begins by cloning the repo using the input argument link. The first if statment evaluets that link and checks if its a valid link to a repo, since this is a valid repo link, we echo "Student repo found". We then cp the file we want into student-submission directory and cd into that directory. The if statment then check if the file exits, which in this case it does, so we echo "file exits". After that we compile the junit test then check if there was a compiler error. Then the tests are ran and the output of the tests are redirected to a file called "results.txt" and we use grep to look into that file for failures and assign that value to a variable testResults. We then check the value of that varaible in the final if statment. Since the value of testResults is not a blank (it should be "Tests run: 3,  Failures: 1"), the else block is exectured and the studnet is given a grade of 0%.

