# AWS Open-ended Capstone Step 8 - Deploy Your Code for Testing

### Description
In this step, I deployed my code to AWS compute resources via EMR Notebook for testing purposes in order to ensure that my code will run smoothly. This step is analogous to deploying my code to a testing environment. I deployed my code, attempted to build a robust test suite, and checked edge cases which would break my code to see if it is performing at the standard I expect it to. In Step 9, I will deploy my finalized code to a production environment. Since I am using EMR Notebook, I will simply set up a new S3 bucket and rerun the code inside EMR Notebook.

At the end of the step, I made sure that my code passes all unit tests so that my dataset utilizes AWS's parallel computing capabilities.

### Deliverables
1. Update project's GitHub repository.
2. Report of unit test outlining the following metrics:
  - Number of Passed/Failed Tests
  - Code coverage percentage

### Unit Tests
In order to complete this, I needed to work with the ```unittest``` Python package.
I basically wanted to ensure that data is being transformed and converted in the desired manner.
Thus, I had to test the data quality to see if files that have been placed into the desired "Data_Stream_1" folder or "Data_Stream_2" folders have the desired column dropped and data type has been successfully casted.

### Issue
While trying to work with EMR Notebook, I tried to work with ```pytest``` via ```pytest-cov``` as well as ```coverage``` package so that I could observe code coverage percentage. Code coverage percentage is basically a measurement of how much of my code includes unit testing.

In order to do code coverage, one needs to do the following:
```
pip install coverage
coverage run -m pytest arg1 arg2 arg3
coverage report -m
```

I assume one needs to pass in the names of Python scripts within desired directory, and then it will report something like:
```
$ coverage report -m
Name                      Stmts   Miss  Cover   Missing
-------------------------------------------------------
my_program.py                20      4    80%   33-35, 39
my_other_module.py           56      6    89%   17-23
-------------------------------------------------------
TOTAL                        76     10    87%
```

This example shows that the first two scripts are well represented by unit tests. One would want a code coverage percentage in the 80% or 89% range to ensure that most of the test cases are implemented.
