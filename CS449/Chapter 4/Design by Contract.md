* Demanding design: assign the responsibility to clients
* Clients check for the condition before calling the method
* Software-to-software communication: trusted clients

# Understanding Precondition and Postcondition in DBC
- They are not input-checking mechanisms
	- DBC applies to *software-to-software communication*, **NOT** software-to-human or software-to-outside-world
- They are not control structures
	- Assertions express correctness conditions
	- If `sqrt()` handles negative arguments a certain way and non-negatives another way, a precondition is not what you need

[[Contract Change|What happens when a contract changes?]]