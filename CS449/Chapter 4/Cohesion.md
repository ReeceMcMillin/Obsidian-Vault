# Cohesion
- The degree to which the elements inside a module belong together
	- High cohesion: the elements inside a module have a high degree of connectedness
- **Good design aims for high cohesion!**
	- Method: statements belong together
	- Class: public constructors & methods belong together
	- Rule of thumb: a descriptive name (is it difficult to summarize functionality?)
# Problems with Low Cohesion
- Difficult to understand, test, maintain, and reuse
	- the `doStuffAndOtherThings()` method
- Perfect cohesion is *not* the goal
	- a module is perfectly cohesive if it only consists of a single, atomic element
	- Such modules are either hardly useful for complex tasks or tightly coupled to other modules
	- Cohesion should be balanced with module compelxity and [[coupling]]