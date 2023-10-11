#cs70 #practice-midterm
2. Warmup: There are 70 people. An even number of them wear one shoe. One-half of the remainder wear no shoes, and the rest wear two shoes. How many shoes are worn in total by the 70 people?
	Answer: 
			 $Shoes = 2k + 2(70-2k/2) + 0(70-2k/2)$
			$Shoes = 2k + 2(70-2k/2)$
			$Shoes = 2k + 70 - 2k$
			$Shoes = 70$
____
 3.  Propositional Logic: Let A, B, and C be statements, where A is always true, B is always false, C is always true, and let P(x) and Q(x) be predicates over a nonempty set S, where the statements ∀x ∈ S, P(x); ∃x ∈ S, Q(x); and ∃x ∈ S, ¬Q(x) are always true.
	 1.  $A \implies B$ : 
		 False, because this is equivalent to true implies false
	 2. $B \implies A$ : 
		 True, because this is equivalent to false implies true. Since B is never true, we never actually have to check if A is true so this is true by default no matter what A is.
	 3. $A \implies C$ : 
		 True, since this is just true implies true.
	 4. $A\vee B\implies\neg C$ : 
		 False, since $A\vee B$ is always true since A is always true. $\neg C$ is false so this is saying true implies false.
	 5. $\neg A \vee C$ : 
		 True, because this is saying false or true.
	 6. $\forall x \in S, Q(x)$ : 
		 False, since we know that there exists an x such that $\neg Q(x)$ meaning this can't be true for all x.
	 7. $\exists x \in S,P(x)$ : 
		 True, since if all x satisfy P(x), there must exist an x that satisfies P(x) or $\forall x \in S(P(x)) \implies \exists x,P(x)$
	 8. $\exists x \in S, Q(x) \wedge P(x)$ : 
		 True, the $P(x)$ portion is redundant since we know all x satisfies this requirement. That means we're just looking for an x that satisfies $Q(x)$ which we know exists.
	 9. $\forall x \in S, Q(x) \vee P(x)$ : 
		 True; this is even easier to prove since statement 8 implies statement 9, meaning this is right by extension.
____
 4. To Prove or Disprove
	 1. Prove or disprove: for $x,y,d \in \mathbb{Z}$ if $d | (x-y)$ then $d | x$  
		 False, counterexample: $$\begin{align} x=13,y=3,d=5 \\d | (x - y) \Rightarrow 5 | (10)\\\neg (5)|13\end{align}$$
	2. Prove or disprove:  $2x^2=4$ has no solutions in the rationals
		True, because there is only one solution for x which we can show here: x can only be equal to $\sqrt 2$ $$\begin{align}2x^2=4\\x^2=2\\\sqrt x = \pm\sqrt 2\end{align}$$
____
 5. Stability in Matchings
	 1. For any stable matching instance, the job optimal stable matching has at least one job that is paired with their favorite candidate. 
		  False, consider the following stable matching where each job has a   candidate that prefers them the least, then no job would get its top job.
		    | 1   | C   | A   | B   |              | A   | 1   | 2   | 3   |          1:    A B, A C, ==C==
		    | 2   | A   | B   | C   |              | B   | 1   | 2   | 3   |         2: C, C B, B A, ==A==
		    | 3   | A  | C   | B   |              | C   | 2   | 1    | 3   |          3: 0, ==B==
		    
	 2. For any stable matching instance, the job optimal stable matching has no job paired with their least favorite candidate.
		False, there could be a case where every job has the same preference list so one job would get their least preferred candidate
		     | 1   | A   | B   | C   |              | A   | 1   | 2   | 3   |          1:    A B C, ==A==
		     | 2   | A   | B   | C   |              | B   | 1   | 2   | 3   |         2: 0, B C, ==B==
		     | 3   | A  | B   | C   |               | C   | 1   | 2    | 3   |          3: 0, 0, ==C==
	 3. For any stable matching instance, the job optimal stable matching has at least one candidate that does not get their favorite job.
		  False, there could be a stable matching where all company and candidate preferences line up
                   | 1   | A   | B   | C   |              | A   | 1   | 2   | 3   |          1:    ==A==
		    | 2   | A   | B   | C   |              | B   | 1   | 2   | 3   |         2:  ==B==
		    | 3   | A   |  B  | C   |              | C   | 1   | 2   | 3   |          3:  ==C==
	 4. For any stable matching instance, all matchings have an even number of rogue couples. (Recall, a stable matching has 0 rogue couples.)
		  True, since stable matchings have 0 rogue couples and 0 is even.
	 5. Consider an output from running the Propose-and-Reject algorithm on a stable matching instance with n jobs and n candidates. We then arbitrarily permute one job’s preference list.
		 1. What is the maximum number of jobs that can participate in a rogue couple in the outputted matching with respect to the permuted preference list?
			   n because if all candidates have the same preference  list and we permute the preference list of the job at the top of all the candidate's lists, this should affect all of them.
		 2. What is the maximum number of rogue couples in the outputted matching with respect to the permuted preference listicle
			   $n$ rogue pairs would occur although I am not sure if my reasoning holds up in the first answer. 
____   
 6. Graphs
	 1. For all $n \geq 3$  any graph with n vertices and n edges is planar.
			  My gut is telling me false but I can't come up with a counterexample so I would probably put true.
	  2. How many colors are needed to vertex color a bipartite graph of maximum vertex degree d.
			  It would be d + 1 since d colors would be used to color the vertices connected to vertex v of degree d and the + 1 color would be used to color v.
	  3. Consider that $G = (V,E1)$ and $G′ = (V,E2)$ are bipartite, how many colors are sufficient to vertex color $G′′ = (V,E1 ∪E2)?$ (You should give as small as bound as possible.)
			I am unsure about this one but I would say $|E_1 \cup E_2| - |E_1 \cap E_2|^\complement$ so that we only get the overlap. This doesn't feel like it's small enough a bound though  since we want to find the max degree. Must review later.
	  4. Consider bipartite graphs $(V,E1),(V,E2),(V,E3),...,(V,Ek)$ are bipartite, how many colors are sufficient to color $(V,E1 ∪ ··· ∪ Ek)?$ (You should give as small as bound as possible that is in terms of k.)
			  We continue the same pattern as before but with $E_k$ 	  
	  5.   There is always a vertex of degree at most in a connected bipartite planar graph. Recall that any bipartite planar graph $G = (V,E)$ satisfies $|E| ≤ 2|V|−4$. (You should give as tight of a bound as possible.)
			Shouldn't this just be 2 since we can kinda zig zag to create a connected bipartite graph? The logic feels a bit iffy though I will admit. Something like this (The graph of S to U). 
			![[Pasted image 20231011012246.png]]
	  6.   The complete graph $K_n$ on $n > 3$ vertices can be made to contain an Eulerian tour by deleting a minimum of edges. (Answer(s) should be as small as possible and possibly in terms of n.)
			  For evens, a eularian tour is possible if every vertex is of even degree but since there is an even number of vertices, each vertex has degree n-1. We should be able to get a eularian tour if we remove n edges. Odds, I think it's zero since  they're all already even.
	  7. Consider a connected n-vertex graph G with exactly k cycles. Provide as tight of a bound as possible for each part. (You may assume $n > 4k$).
		  1. Removing 2k edges from G produces a graph with at least __ connected components
				  
		  1. Removing 2k edges from G produces a graph with at most connected components.
	  8. At least d colors are required for a valid vertex coloring for any graph with maximum vertex degree d.
			  False, you would need d + 1 in order to color vertex v.
	  9.  Removing any degree 2 vertex (and its incident edges) in a connected acyclic graph leaves a graph with two connected components.
			  True, as that degree 2 vertex is the only thing keeping the components together. If there existed another vertex attached to these components, it would form a cycle.
	  10. Consider a walk in a connected graph $G = (V,E)$ with $|V| ≥ 4$ formed by starting at a vertex $u$ and proceeding by choosing an arbitrary unused edge at the current vertex to get to the next vertex. The process terminates when it reaches a vertex where all incident edges have already been used.
		  1. The walk always terminates at the vertex u if and only if the degree of every vertex is .
				  0
		  2. For a tree, the walk always terminates at a vertex with degree that is . (Give as specific of an answer as possible.)
				  odd
		  3. For a complete graph on n vertices where n is odd, the walk always forms a Hamiltonian tour.
				  True
		  4. For a hypercube of dimension n, the walk terminates at an odd degree vertex or at u.
				  True
  ___
  7. Mod Math
	  1. Give all the solutions to $5x ≡ 3$(mod 24) or write “none”.
		  Im assuming this is all x mod 24 but 15, 57 just in case
	  2. Give all the solutions to $15x ≡ 3$(mod 24) or write “none”.
		  5
	  3. Give all the solutions to $15x ≡ 13$ (mod 24) or write “none”.
		  None
	  4. Compute $21^{141} (mod 71)$ .
		  21
	  5. Consider an RSA scheme with public key $N = 77$ and $e = 7$.
		  1. What is the private key?
			  d=43
		  2. What is the decoding of the encrypted message 76?
			  This is a hail mary but 1?
	  6. What is $304^{2022}$mod(70)?
		  16
8. Given a positive integer n, we define the digital root of n, DR(n), to be the positive integer attained from repeatedly summing the base 10 digits of n until n is a single digit number. For example, DR(191) = 2 because 191 → 1+9+1 = 11 → 1+1 = 2. Prove that DR(n) ≡ n (mod 9).
	For n of k digits long, we can rewrite n as $a*10^{k-1} + b*10^{k-2}... + c*10^0$ . We know that any power of 10 is equal to 1(mod9) since a multiple of 9 is 9, 99, 999 and so on. This means the original equation can be rewritten as $9(a + b + c) + a + b + c$. The a + b + c in the parentheses would have coefficients but they won't matter after this next step. $9(a + b + c) + a + b + c = a + b + c$(mod9). Now, if a + b + c is less than 9, we're done, but if not, a + b + c = d x 10 + e which again, d x 10 = dmod(9) and c = c mod(9) so we're left with d + e. We just proved that repeatedly adding the digits is the same as modding by 9. Wow I can't believe I was actually able to do that!
 ___
 9. Polynomials and Applications
	 1. Consider non-zero polynomials $P(x)$ of degree $d_p$ and $Q(x)$ of degree $d_q$, where $d_p$ and $d_q$ are nonnegative integers
		 1. What is the maximum degree of $P(x)Q(x)$?
			 dp + dq
		 2. What is the maximum degree of $P(Q(x))$?
			 dq x dp
		 3. What is the maximum degree of $P(xQ(x))$?
			 (dq+1) x dp
	 2. If a polynomial $P(x)$ has a root at r, then $P(x) = (x - r)Q(x)$ for some $Q(x)$ 
		 True, Q(x) would be some polynomial of degree 1 less than P(x)
	 1. Given a degree d polynomial $P(x)$ and $k$ values $x_1,..., x_k$ with $k ≤ d$, how many polynomials of degree at most d over arithmetic modulo prime p have the same value as $P(x) on x_1,..., x_k$?
		 0? I need to review polynomial division
	 4. For this problem, consider the Berlekamp-Welch scheme.
		 1. What is the degree of polynomial P(x) used to encode this message?
			 n - 1
		 2. What is the degree of the error locator polynomial E(x)?
			  k
		 3. What is the degree of Q(x) = P(x)E(x)?
			  n + k
		 4. If there were i ≤ k errors, the recovered E(x) has at least roots. Give the largest lower bound you can.
			 k
___
10. Polynomials and Functions
	1. Consider any function f(x) where the domain and range is arithmetic modulo a prime p
	2. Prove that f(x) corresponds to a polynomial expression modulo p.
		Not sure how to answer this
	2. Give a tight upper bound on the minimum degree of a polynomial that represents f(x)
___
11. 
