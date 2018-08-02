## Read Me ##

** rcx-api-test automation suite** is build on top of KARATE and CUCUMBER frameworks for running api test cases for real time scenarios without human interaction for faster execution and accurate results.

### Tools/Software required for setting up ###
- IntelliJ IDEA / Eclipse.
- KARATE DSL libraries. (step definition wraper)
- Cucumber-JVM libraries. (feature file(s) and runner)
- Maven (Building)
- Jenkins (CI)
- Git
- JDK 1.8.0_171 Or higher

### Folder Structure


```
src/test/java
    |
    \-- src
        |
        +-- features
			|-- Product
				|--Service
					|-- Functional Area-1
						|
						+-- TCXXX.feature
						+-- TCXXX.feature
					|-- Functional Area-2
						|
						+-- TCXXX.feature
						+-- TCXXX.feature						
        +-- payloads
        |   |
        |   +-- model_schema_1.json
        |   +-- model_schema_2.json
        |
		+-- resources
        |   |
        |   +-- config.properties
        |   +-- log4j.properties
        |
		+-- utils
        |   |
        |   +-- utils.js
        |   +-- resuable.js
        |
		+-- runner
        |   |
        |   +-- KarateRunnerTest.java
		|
		+-- karate-config.js
		+-- logback-test.xml
		+-- log4j2.properties
	|
	+ pom.xml
			
```


### Setting up Jbehave Suite ###

- Checkout the code from Git
	> git clone https://xxxxxxxxxxxx.git
- Import the project into IntelliJ IDEA as maven.
- All the Automation Framework dependency jars will be downloaded to the project.
- Make sure all the Karate, Cucumber and JDK dependency jars are in classpath.

 **Voila** Your project is ready for execution.
 
### Plug-ins in Eclipse or IntelliJ
 - If you use the open-source [Eclipse Java IDE](http://www.eclipse.org), you should consider installing the free [Cucumber-Eclipse plugin](https://cucumber.io/cucumber-eclipse/). It provides syntax coloring, and the best part is that you can 'right-click' and run Karate test scripts without needing to write a single line of Java code.
 
 - if use [IntelliJ](https://www.jetbrains.com/idea/), Cucumber support is [built-in](https://www.jetbrains.com/idea/help/cucumber.html) and you can even select a single [`Scenario`](#script-structure) within a `Feature` to run at a time.

 
### Parallel Execution
Framework can run tests in parallel, and dramatically cut down execution time. This is a 'core' feature and does not depend on JUnit, TestNG or even Maven. Just we need to pass thread cound from command parameter as '-Dthread.count=5'.

 
### Execution of test cases from command line / IntelliJ IDE###

##Execute all test(s)
mvn clean test

##Tag Level - Execution (will execute only tag specific)
mvn clean test -Dcucumber.options="--tags @smoke"

##Multi-Tag Level - Execution (will execute only tag specific)
mvn clean test -Dcucumber.options="--tags '@smoke, @regression' "

##Folder Level - Execution (will execute only specific folder of feature(s))
mvn clean test -Dcucumber.options="classpath:features/rcx_core/crud_api/basic_crud/members"

##Folder Level With Tags (will execute only specific folder of feature(s) with specific tag)
mvn clean test -Dcucumber.options="classpath:features/rcx_core/crud_api/basic_crud/members --tags @regression"

##Folder Level with multi-Tags (will execute only specific folder of feature(s) with specific multi-tag(s))
mvn clean test -Dcucumber.options="classpath:features/rcx_core/crud_api/basic_crud/members --tags '@smoke, @regression' " 

	  
### Extracting results/reports ###
- All the results are stored under target/cucumber-html-reports.
- All the results are stored in html format.

	 * `results path : target/cucumber-html-reports/features`

---


