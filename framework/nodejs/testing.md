## Automated Tests
Benefit of automated test
- Test your code frequestly, in less time.
- Catch bugs before deploying
- Deploy with confidence
- Refactor with confidence
- Focus more on the quality
Type of test are unit test, integration test and end-to-end test. 
     
### 1. Unit testing
Testing a unit of application with its external dependencies.     
test a class or multiple classes without its external dependencies  
fast & cheap but don't give confidance.  

### 2. Integration testing
Testing application with its external dependencies.  
test integration of code with external dependenices.  
(traditional definition) Testing two or more unit as whole.  
provide applications of end-to-end test without having to go through ui.  

### 3. End-To-End testing
Drives an application through its UI.   
give you the greatest confidence & very slow & very brittle.  


### Test pyramid
- favour unit tests to e2e tests.
- cover unit tests gaps
- user end-to-end tests sparingly.


### Jest
framework for writing test.
