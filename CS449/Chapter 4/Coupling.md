# Coupling
- degree of interdependence between modules
	- or the *strength* of relationships between modules
- Consequence of tight coupling
	- A change to module `P` can requier a corresponding change to module `Q`.
	- If the latter is not made, it leads to faults
- **Good design aims for loose coupling!**

# Coupling Criteria
- Size
	- number of connections between modules
	- `m1(x)` is more loosely coupled to methods that call it than `m1(x, y, z, w, v, u)`
- Visibility
	- prominence of the connection between two modules
	- passing data in a parameter list is making an obvious connection: **good**
	- modifying global data so that another module can use that data is a *sneaky connection*: **bad**
- Flexibility
	- how easily can the connections between modules be changed?

# Example - Remote
- Consider the example of a remote in Ch04-1
	- A remote that controls a `SamsungTV` directly is too tightly-coupled.
	- A remote that controls an abstract `TV` class that `SamsungTV` inherits from is more loosely coupled and a better design.