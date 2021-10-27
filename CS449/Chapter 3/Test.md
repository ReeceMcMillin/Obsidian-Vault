# What is a Test?
- Context
	- the precondition under which the test can be performed
- Input
	- inputs from stdio/method calls
- Oracle
	- Expected result (**oracle value**) and comparison
	- assertions
- Test execution: pass or fail
	- Actual result == oracle value?
	- Failure: either program *or test* has a problem
- Complex Test
	- Test context + a sequence of test inputs/oracles
- Test Suite
	- A set of tests and/or test suites

# xUnit
- Collective name for several unit testing frameworks
- TestCase: the base class extended by all unit tests
- Test Runner: runs tests and reports the test results
- Test Fixtures/Contexts
	- The set of [[Preconditions and Postconditions|preconditions]] needed to run a test
	- The developer should set up a known good state before the tests and return to the original state after the tests
- Test Case object: a set of tests (test methods) that all share the same fixture
	- The order of tests shouldn't matter

# jUnit Tests
- setUp and tearDown
	- Multiple tests may share the same test objects
	- `setUp()`
		- shared test setup code
		- called before each test method
		- make the local variables into instance variables
	- `tearDown()`
		- clean up of the test fixture
		- called after *each* test method

# From AC to Acceptance Tests
- Refine each AC with *specific* context, input values, and expected results
	- given/when:
		- set up context/precondition
		- exercise functionality (test input, method call)
	- then:
		- oracle
		- check postconditions (assertions)
- Test execution: automated vs. manual

# Acceptance Tests vs. Unit Tests
- Acceptance Tests
	- On the level of a user story (AC)
	- Typically black-box tests (not necessarily test code, though can be written like unit tests)
- Unit (Developer) Tests
	- On the level of code units (function/method, class, module)
	- Test code (likely white-box tests if not TDD)
	- Not necessarily corresponding to acceptance criteria, although written as unit tests
	- 