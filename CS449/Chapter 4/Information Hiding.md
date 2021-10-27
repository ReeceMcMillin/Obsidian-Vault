# Information Hiding
- Make the info inside a module invisible to the module's clients
	- Data structures and implementation details
- Public method
	- visible: signature, pre/post-condition
	- hidden: method body
- Class
	- visible: public constructors and methods
	- hidden: private variables and methods

# Guidelines
- Make instance variables private
- provide public getters/setters if necessary
- avoid excessive unnecessary getters/setters