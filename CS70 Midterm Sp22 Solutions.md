5.4 Question: 4. For any stable matching instance, all matchings have an even number of rogue couples. (Recall, a stable matching has 0 rogue couples.)
	I thought that  a stable matching wouldn't have a rogue couple and since 0 is even, then problem solved. I interpreted the question incorrectly. The problem asked about any possible stable matching. They didn't necessarily have to be valid.![[Pasted image 20231011210602.png]]
5.5.1 What is the maximum number of jobs that can participate in a rogue couple in the outputted matching with respect to the permuted preference list?
	I misread the question. Make sure to read thoroughly! I was thinking of candidates that could be affected when it was really only asking about the job. Even then though, I probably still would have put n. Make sure to deeply understand why it's only 1. I thought that 1 job would screw up a ton of other jobs since the candidates the other jobs would've been matched with are now going to the permuted job, messing up their candidate pairings too!![[Pasted image 20231011211202.png]]
	Ok so all the other jobs that are paired with new candidates c are still valid since the candidates that j preferred would still reject j. I was thinking of how many jobs would be affected rather than how many would form rogue couples.
	
5.5.2 What is the maximum number of rogue couples in the outputted matching with respect to the permuted preference listicle
	I based this off of my answer in 5.5.1 so the logic was shaky from the start. Without looking at the answer, I think that since only one job can participate in rogue couples, the answer is n-1 since one job would be valid and the rest are invalid.

6.1 For all n ≥ 3, any connected graph with n vertices and n edges is planar.
	I put true so I would have gotten this right but I was unsure in my reasoning. A graph with n veretices and n edges is just a tree with an additional edge. All trees are planar and adding an edge won't make it non-planar since there is always a path between two vertices. A tree only has one face so it is impossible to create a crossing.

6.2 How many colors are needed to vertex color a bipartite graph of maximum vertex degree d? (Recall that a valid vertex coloring assigns colors to the vertices such that the vertices in an edge have different colors.)
	I was thinking of edge coloring which is why I got it wrong. We know that any bipartite graph is 2 colorable and any planar graph is 4 colorable.
6.3 Consider that $G = (V,E1)$ and $G ′ = (V,E2)$ are bipartite, how many colors are sufficient to vertex color $G ′′ = (V,E1 ∪E2)?$ (You should give as small a bound as possible.)
	Yikes, I got almost all  of these wrong.![[Pasted image 20231011213923.png]]