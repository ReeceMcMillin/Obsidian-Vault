# Separation of Concerns
- Separate a program into distinct modules such that each module addresses a separate concern
	- facilitate module upgrade, reuse, and independent development
- General concerns (website):
	- organization of webpage content: **HTML**
	- content presentation style: **CSS**
	- how the content interacts and behaves with the user: **JavaScript**
- Specific concerns
	- Audit log of login
	- print of a sales report

# Crosscutting Concerns
- Crosscut many modules
	- Error handling, logging, data persistence, security, etc
- Usually viewed as secondary concerns
	- The classes and methods address the primary concerns of business goals
- Cannot be modularized using the modularization mechanisms in object oriented or procedural languages
	- They inherently follow different rules for functional decomposition
	- Scattered in multiple modules ("tangled")
- Solution: Aspect-Oriented Programming
- 