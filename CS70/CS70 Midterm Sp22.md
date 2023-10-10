2. Warmup: There are 70 people. An even number of them wear one shoe. One-half of the remainder wear no shoes, and the rest wear two shoes. How many shoes are worn in total by the 70 people?
	1. Answer: 
			 $Shoes = 2k + 2(70-2k/2) + 0(70-2k/2)$
			$Shoes = 2k + 2(70-2k/2)$
			$Shoes = 2k + 70 - 2k$
			$Shoes = 70$
 3.  Propositional Logic: Let A, B, and C be statements, where A is always true, B is always false, C is always true, and let P(x) and Q(x) be predicates over a nonempty set S, where the statements ∀x ∈ S, P(x); ∃x ∈ S, Q(x); and ∃x ∈ S, ¬Q(x) are always true.
	 1.  $A \implies B$ : False, because this is equivalent to true implies false
	 2. $B \implies A$ : True, because this is equivalent to false implies true. Since B is never true, we never actually have to check if A is true so this is true by default no matter what A is.
	 3. $A \implies C$ : True, since this is just true implies true.
	 4. $A\vee B\implies\neg C$ : False, since $A\vee B$ is always true since A is always true. $\neg C$ is false so this is saying true implies false.
	 5. $\neg A \vee C$ : True, because this is saying false or true.
	 6. $\forall x \in S, Q(x)$ : False, since we know that there exists an x such that $\neg Q(x)$ meaning this can't be true for all x.
	 7. $\exists x \in S,P(x)$ : True, since if all x satisfy P(x), there must exist an x that satisfies P(x) or $\forall x \in S(P(x)) \implies \exists x,P(x)$
	 8. $\exists x \in S, Q(x) \wedge P(x)$ : True, the $P(x)$ portion is redundant since we know all x satisfies this requirement. That means we're just looking for an x that satisfies $Q(x)$ which we know exists.
	 9. $\forall x \in S, Q(x) \vee P(x)$ : True; this is even easier to prove since statement 8 implies statement 9, meaning this is right by extension.
	 10.==Does this work? Wow!==