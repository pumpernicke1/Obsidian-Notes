- What does it mean for a function to be computable? 
	- A function is computable when it can be run and solved by a computer
- Is there an example of a function that's not computable?
	- The halting problem: ![[Pasted image 20231017132031.png]]
- How do we determine and prove computability?
	- Step 1: Use intuition to determine computability. If the program looks close to the halting problem, then it is most likely not computable
	- Step 2: Sketch out an algorithm for the program in pseudocode
	- Step 3: Prove uncomputability
		- To do this, try to recreate the halt problem with the given program. This way we get $\exists solve x \implies \exists halt$ and we know halt doesn't have a solution so we know that the program is incomputable
	- ==Ex:==
```
	def testZeroOne(P, x) :
		//does P(x) return a zero division error
		
	def halt(P, x) :
		def Q(y) : //testZeroOne is Q
			halt(P, x)
			return 1/0
		return testZeroDivide(Q,x)

	def halt(P, x) :
		def Q(y) :
			run P(x)
			print "hello word"
		return TestHelloWorld(Q, x)

```
No because we wouldnt be able to determine if it halted before printing ABC since that's the first thing we're supposed to do

True: I think it is countably infinite
False: This is an infinite sequence of infinitely long bitstrings so uncountable
True? Not so sure I need to review computability some more when I get home