## Backtracking, Recursion, and Dynamic Programming

From WikiPedia:

> **Dynamic programming **is a method of solving complex problems by breaking them down into simpler steps. It is applicable to problems that exhibit the properties of overlapping subproblems which are only slightly smaller and optimal substructure.
>
> **Backtracking **is a general algorithm for finding all \(or some\) solutions to some computational problem, that incrementally builds candidates to the solutions, and abandons each partial candidate c \("backtracks"\) as soon as it determines that c cannot possibly be completed to a valid solution.
>
> **Recursion: **In mathematics and computer science, a class of objects or methods exhibit recursive behavior when they can be defined by two properties:
>
> 1. A simple base case \(or cases\)—a terminating scenario that does not use recursion to produce an answer
> 2. A set of rules that reduce all other cases toward the base case

Conclusion:

> 1. Dynamic programming is a method for solving a complex problem by breaking it down into **a collection of simpler subproblems**. It is applicable to problems exhibiting the properties of overlapping subproblems and optimal substructure. At each subproblem level, it searches for the optimal option.
> 2. Where as Backtracking is** a refinement of the brute force approach**, which systematically searches for a solution to a problem among all available options. **A specific form of DFS.**
> 3. Recursion is a function that calls itself, it can be used to solve backtracking or dp problems
> 4. There are two typical implementations of Dynamic Programming approach:_bottom-to-top\_and\_top-to-bottom_.
>    1. _Top-to-bottom Dynamic Programming \_is nothing else than ordinary \_recursion_, enhanced with memorizing the solutions for intermediate sub-problems.
>    2. In \_Bottom-to-top Dynamic Programming, \_the approach is also based on storing sub-solutions in memory, but they are solved in a different order \(from smaller to bigger\), and the resultant general structure of the algorithm is not recursive

### Reference

1. [https://tp-iiita.quora.com/Dynamic-Programming-Part-1](https://tp-iiita.quora.com/Dynamic-Programming-Part-1)
2. [https://www.quora.com/What-is-the-difference-between-dynamic-programing-and-backtracking](https://www.quora.com/What-is-the-difference-between-dynamic-programing-and-backtracking)
3. [http://stackoverflow.com/questions/3592943/difference-between-back-tracking-and-dynamic-programming](http://stackoverflow.com/questions/3592943/difference-between-back-tracking-and-dynamic-programming)



