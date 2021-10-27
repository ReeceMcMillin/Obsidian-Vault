# Contract Change
- What happens if we rename a method, change the return type, or change an argument type?
	- Suppose the method is being used by another piece of code
	- Syntax error - all client code needs to be updated
- What happens if we don't change the message signature, but the body? Do we need to update the client code?
	- Have the pre/postcondition (meanings) changed?
- Different reasons for change

# Impacts of Contract Change
- `int foo(int x)`
	- precondition `x > 5`, postcondition `foo(x) > 0`
- Client code
	```c
	int x = ... //assume 6
	assert(x > 5);
	int y = foo(x);
	assert(y > 0);
	```
- New precondition: `x > 10`
	- Our original `x > 5` assertion is now incorrect.
	- `x = 6` in the client code still passes, but betrays the precondition.
	- These errors can be **very** hard to detect.
- No postcondition: `foo(x) >= 0`

# Rule of Contract Change
- A **safe change** to a method may replace the existing
	1. precondition by an equal or **weaker** one
	2. postcondition by an equal or **stronger** one
	- This means the existing client will not be affected.
- P1 is stronger than P2 if P1 implies P2
	- P2 is weaker than P1