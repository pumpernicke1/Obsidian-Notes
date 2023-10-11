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
	 1. Consider an output from running the Propose-and-Reject algorithm on a stable matching instance with n jobs and n candidates. We then arbitrarily permute one job’s preference list.
		 1. What is the maximum number of jobs that can participate in a rogue couple in the outputted matching with respect to the permuted preference list?
			   n because if all candidates have the same preference  list and we permute the preference list of the job at the top of all the candidate's lists, this should affect all of them.
		 1. What is the maximum number of rogue couples in the outputted matching with respect to the permuted preference listicle
			   n^2 although I am not sure if my reasoning holds up in the first answer. 