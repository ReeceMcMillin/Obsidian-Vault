# Modularity
- the degree to which components of a system are *separated*
- A modular design divides complex software into uniquely named compnents (*modules*)
	- after the modules are developed, they're integrated to meet requirements
- divide and conquer
	- solve a complex problem by breaking it into manageable pieces
- typical modules
	- method, class, interface, package

# Problems
- Inflexible to deal with requirements change
	- the entire main method must change
	- hardly reusable for new requirements
- not unit-testable
- in essence: **inadequate requirements analysis**

# Features
- Decomposability
	- the extent to which the problem can be broken into sub-problems with simple relations
- Composability
	- the extent to which those sub-problems can be reassmbled as a solution
- Plug and Play
	- Modules should be reusable
- Testable
	- Modules should be testable and confine runtime exceptions and errors to very few modules