# Correctness Formula
## Hoare Triples
* {P} A {Q}
	* A: method (or program)
	* P: precondition, logical constraint on input
	* Q: postcondition, logical constraint on output
	* "Any execution of A, starting in a state where P holds, will *terminate* in a state where Q holds."

* `{x >= 9} x := x + 5; {x >= 13}`
	* is this true? seems like it!
		* what about overflows?
		* even if the postcondition is met, it's not as meaningful as it could be. `x >= 14` is more specific and still true.

* Pre/postcondition capture essential semantics
	* Constraints on the input/output
* A method's pre/postcondition may involve
	* explicit parameters, global/instance variables
	* other methods
	* other object states
* pre/postcondition specifies what, not how
	* can be independent of implementation
		* stack: `s.push(x)`'s postcondition: `s.peek() == x`
	* "how to do" is the job of the method body
### Pre/Postcondition: int max(int[] list)
* precondition: `list.length > 0`
* postcondtion:
	* `max >= list[i] for each i (0 <= i < list.length`
		* `max` is *at least* larger than every element in `list`
	* there exists `j (0 <= j < list.length)` such that `max = list[j]`
		* `max` is actually an element of `list`

### Sorting: int[] sort(int[] p)
* is the postcondition correct?
	* precondition: p.length > 0
	* postcondition: `p.length = q.length` and `q[0] <= q[1] <= ... <= q[n-1]`
		* there should be as many elements in the input list as the output list
		* the elements in the output list should be ordered from least to greatest
	* what if you designed an algorithm that transformed every element of `p` into a `1`? It'd satisfy the postcondition!
		* **This means our postcondition is wrong.**
	* is this postcondition correct?
		* `p.length = q.length` and `q[0] <= ... <= q[n-1]`
		* for any `i` in `p`, there is `j` in `p` such that `p[i] = q[j]`
		* for any `i` in `q`, there is `j` in `p` such that `q[i] = p[j]`
### Sorting - Formal Pre/Postconditions
* Sort: int[] sort(int[] p)
* Precondition:
	* `p.length > 0`
* Postcondition:
	* `haveTheSameSize(p, q): p.length = q.length`
	* `isSorted(q): ∀ i, 1 ≤ i ≤ p.length − 1 ⇒ q[i] ≤ q[i+1]`
	* `isPermutation(p, q): ∀ x, count(x, p) = count(x, q)`
		* `count(x, p): number of times x occurs in p`

### Pre/Postcondition Exercises
* `int[] reverse(int[] list)`
	* Precondition:
		* `list.length > 0`
	* Postcondition:
		* for all `0 <= i < list.length`, `p[i] = q[list.length - i - 1]`.
* `int[] linearSearch(int[] list, int key)`

### Options of Precondition Design
* Assumed Precondition: **[[Design by Contract]]**
	* Demanding design: assign responsibility to clients
	* Clients check for condition before calling method
	* Software-to-software communication: trusted clients
* Validated Precondition: **[[Defensive Programming]]**
	* Tolerant design: the condition will appear in an `if-then` or equivalent control structure *within* the method
	* Software-to-human or software-to-outside-world: untrusted environments
	* VERY important for safety/security-critical software