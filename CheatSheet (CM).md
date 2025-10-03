This is your new *vault*.

Make a note of something, [[create a link]], or try [the Importer](https://help.obsidian.md/Plugins/Importer)!

When you're ready, delete this note and make the vault your own.
LeetCode CheatSheet [source](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/713/interviews-and-tools/4547/)

- ### ⬜️ Time complexity (Big O) cheat sheet
    
    - ![](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/713/interviews-and-tools/Figures/DSA/Chapter_11/big_o.png "big O chart")
    - ⬜️ Complexity of common operations split by...
        - ⬜️ data structure/algorithms...
            - ❓ **Arrays (dynamic array / list)**
                - ❓ Given `n = arr.length`,
                    - ❤️❓ Add or remove element at the end: 
                        - ❤️❓ O(1) [amortized](https://stackoverflow.com/questions/33044883/why-is-the-time-complexity-of-pythons-list-append-method-o1)
                            - ❓ "It's amortized O(1) time complexity, not literally O(1)"
                                - ✅ Let's say the list reserved size is 8 elements and it doubles in size when space runs out.
                                - ⬜️ You want to push 50 elements.
                                - ⬜️ The first 8 elements push in O(1).
                                - ✅ The ninth triggers reallocation and 8 copies, followed by an O(1) push.
                                - ✅ The next 7 push in O(1).
                                - ✅ The seventeenth triggers reallocation and 16 copies, followed by an O(1) push.
                                - ✅ The next 15 push in O(1).
                                - ⬜️ The thirty-third triggers reallocation and 32 copies, followed by an O(1) push.
                                - ✅ The next 31 push in O(1).
                                - ✅ This continues as the size of list is doubled again at pushing the 65th, 129th, 257th element, etc..
                                - ✅ So all of the pushes have O(1) complexity, we had 
	                                - 64 copies at O(1), and 
	                                - 3 reallocations at O(n), with 
		                                - n = 8, 16, and 32.
                                - ❓ Note that this is a **geometric series** and asymptotically equals O(n) with n = the final size of the list.
									- ❓ What is a geometric series?
											- A **geometric sequence** is a sequence where each term is obtained by multiplying the previous term by a fixed ratio rrr. [Wikipedia+1](https://en.wikipedia.org/wiki/Geometric_progression?utm_source=chatgpt.com)  
											    So if the first term is aaa, the terms are
											    
											    a,  ar,  ar2,  ar3,  …a,\; ar,\; ar^2,\; ar^3,\; \dotsa,ar,ar2,ar3,…
											- A **geometric series** is the _sum_ of the terms of a geometric sequence.  
											    So you write:
											    
											    a+ar+ar2+ar3+⋯a + ar + ar^2 + ar^3 + \cdotsa+ar+ar2+ar3+⋯
											
											---
											
											## Finite geometric series
											
											If you sum up to nnn terms (from term 0 up to term nnn), the partial sum is:
											
											Sn=a+ar+ar2+⋯+arn=∑k=0nark.S_n = a + ar + ar^2 + \cdots + ar^n = \sum_{k=0}^n a r^k.Sn​=a+ar+ar2+⋯+arn=k=0∑n​ark.
											
											When r≠1r \neq 1r=1, there is a standard closed-form:
											
											Sn=a⋅1−r n+11−r.r≠1(if )S_n = a \cdot \frac{1 - r^{\,n+1}}{1 - r}. \tag{if } r \neq 1Sn​=a⋅1−r1−rn+1​.r=1(if )
											
											If r=1r=1r=1, then each term is just aaa, so summing n+1n+1n+1 terms gives Sn=a(n+1)S_n = a (n+1)Sn​=a(n+1). [ChiliMath+3Wikipedia+3Lumen Learning+3](https://en.wikipedia.org/wiki/Geometric_series?utm_source=chatgpt.com)
											
											---
											
											## Infinite geometric series & convergence
											
											If you let n→∞n \to \inftyn→∞, you get an **infinite geometric series**:
											
											a+ar+ar2+ar3+⋯=∑k=0∞ark.a + ar + ar^2 + ar^3 + \cdots = \sum_{k=0}^\infty a r^k.a+ar+ar2+ar3+⋯=k=0∑∞​ark.
											
											This infinite sum **converges** (i.e. has a finite value) **if and only if** ∣r∣<1\lvert r \rvert < 1∣r∣<1. [Wikipedia+3Wikipedia+3Lumen Learning+3](https://en.wikipedia.org/wiki/Geometric_series?utm_source=chatgpt.com)
											
											In that case, since rn+1→0r^{n+1} \to 0rn+1→0 as n→∞n \to \inftyn→∞, the formula becomes:
											
											S=lim⁡n→∞Sn=lim⁡n→∞a1−r n+11−r=a1−r.S = \lim_{n\to\infty} S_n = \lim_{n\to\infty} a \frac{1 - r^{\,n+1}}{1 - r} = \frac{a}{1 - r}.S=n→∞lim​Sn​=n→∞lim​a1−r1−rn+1​=1−ra​.
											
											If ∣r∣≥1\lvert r \rvert \ge 1∣r∣≥1, the series **diverges** — it does not sum to a finite number. [Wikipedia+2Wikipedia+2](https://en.wikipedia.org/wiki/Geometric_series?utm_source=chatgpt.com)
											
											---
											
											## Examples
											
											1. **Convergent infinite series**
											    
											    1+12+14+18+⋯1 + \tfrac12 + \tfrac14 + \tfrac18 + \cdots1+21​+41​+81​+⋯
											    
											    Here a=1a = 1a=1, r=12r = \tfrac12r=21​. Since ∣r∣=12<1\lvert r \rvert = \tfrac12 < 1∣r∣=21​<1, it converges. The sum is
											    
											    11−12=2.\frac{1}{1 - \tfrac12} = 2.1−21​1​=2.
											2. **Divergent series**
											    
											    2+4+8+16+⋯2 + 4 + 8 + 16 + \cdots2+4+8+16+⋯
											    
											    Here a=2a = 2a=2, r=2r = 2r=2. Since ∣r∣=2>1\lvert r \rvert = 2 > 1∣r∣=2>1, the series diverges — it grows without bound.
											    
											1. **Finite sum example**  
											    Sum the first 5 terms of 3+6+12+24+483 + 6 + 12 + 24 + 483+6+12+24+48.  
											    Here a=3a = 3a=3, r=2r = 2r=2, and n=4n = 4n=4 (since term 0 through term 4).  
											    Use:
											    
											    S4=31−251−2=31−32−1=3⋅31=93.S_4 = 3 \frac{1 - 2^{5}}{1 - 2} = 3 \frac{1 - 32}{-1} = 3 \cdot 31 = 93.S4​=31−21−25​=3−11−32​=3⋅31=93.
											
											---
											
											## Key takeaways & warnings
											
											- Always check the **common ratio** rrr. That’s the linchpin for convergence.
											    
											- The infinite sum formula a1−r\frac{a}{1-r}1−ra​ is only valid when ∣r∣<1\lvert r \rvert < 1∣r∣<1.
											    
											- If ∣r∣≥1\lvert r \rvert \ge 1∣r∣≥1, the infinite series diverges (unless one is doing some advanced summation techniques beyond standard real analysis). [Wikipedia+1](https://en.wikipedia.org/wiki/Divergent_geometric_series?utm_source=chatgpt.com)
											    
											- Be careful with negative rrr: alternating signs can complicate things, but the same convergence rule ∣r∣<1\lvert r \rvert < 1∣r∣<1 applies.
											    
											
											---
											
											If you want, I can walk through geometric series in a programming or algorithmic context (how to sum them efficiently, error bounds, etc.), or show proofs. Do you want me to go further in one of those directions?
                                - ⬜️ That means 
	                                - the whole operation of pushing n objects onto the list is 
		                                - O(n).
                                - ❤️ If we _amortize_ that per element, it's O(n)/n = O(1).
                            - ⬜️ What does amortized mean?
                                - ⬜️ To pay off a debt gradually over a set period with regular payments that cover both principal and interest, or to gradually write off the cost of an intangible asset by expensing it over its useful life
							- ❓Why would removing an element from the end of an array still be amortized? are we resizing to make the array smaller as well? 
                    - ✅ Add or remove element from arbitrary index: 
                        - O(n)
                    - ✅ Access or modify element at arbitrary index: 
                        - O(1)
                    - ✅ Check if element exists: 
                        - O(n)
                    - ✅ Two pointers: 
                        - ✅ $O(n⋅k)$, where $k$ is the work done at each iteration, includes sliding window
                    - ❓ Building a prefix sum: 
                        - ❓Hint / Example of prefix sum: 
	                        - ❓
                        - Answer:
	                        - O(n)
                    - ❓ Finding the sum of a subarray given a prefix sum: 
                        - O(1)
            - ⬜️ **Strings (immutable)**
                - ⬜️ Given ,
                    - ⬜️ Add or remove character:
                        - ⬜️ O(n)
	                        - ⬜️ because you have to rewrite the string in order in memory
                    - ✅ Access element at arbitrary index: 
                        - O(1)
                    - ✅ Concatenation between two strings: 
                        - ❤️ $O(n+m)$, where $m$ is the length of the other string
                    - ✅ Create substring: 
                        - $O(m)$, where $m$ is the length of the substring
                    - ⬜️ Two pointers: 
                        - ✅ $O(n⋅k)$, where $k$ is the work done at each iteration, includes sliding window
                    - ✅ Building a string from joining an array, string builder, etc:
                        - $O(n)$
            - ⬜️ **Linked Lists**
                - ⬜️ Given $n$ as the number of nodes in the linked list,
                    - ⬜️ Add or remove element given pointer before add/removal location: 
	                    - $O(1)$
                    - ⬜️ Add or remove element given pointer at add/removal location: 
                        - $O(1)$ if doubly linked
                    - ⬜️ Add or remove element at arbitrary position without pointer: 
                        - $O(n)$
                    - ⬜️ Access element at arbitrary position without pointer: 
                        - $O(n)$
                    - ⬜️ Check if element exists: 
                        - $O(n)$
                    - ⬜️ Reverse between position  and : 
                        - $O(j−i)$
                    - ⬜️ Detect a cycle: 
                        - $O(n)$ using fast-slow pointers or hash map
            - ⬜️ **Hash table/dictionary**
                - ⬜️ Given ,
                    - ⬜️ Add or remove key-value pair: 
                        - $O(1)$
                    - ⬜️ Check if key exists: 
                        - $O(1)$
                    - ⬜️ Check if value exists: 
                        - $O(n)$
                    - ⬜️ Access or modify value associated with key: 
                        - $O(1)$
                    - ⬜️ Iterate over all keys, values, or both: 
                        - $O(n)$
                - ⬜️ Note:
                    - ⬜️ the $O(1)$ operations are constant relative to .
                    - ⬜️ In reality, the hashing algorithm might be expensive.
                    - ⬜️ For example, if your keys are strings, then it will cost $O(m)$ where $m$ is the length of the string.
                    - ⬜️ The operations only take constant time relative to the size of the hash map.
            - ⬜️ **Set**
                - ⬜️ Given ,
                    - ⬜️ Add or remove element: 
                        - ⬜️ $O(1)$
                    - ⬜️ Check if element exists: 
                        - ⬜️ $O(1)$
                - ⬜️ The above note applies here as well.
            - ⬜️ **Stack**
                - ⬜️ Stack operations are dependent on their implementation.
                    - ⬜️ A stack is only required to support pop and push.
                        - ⬜️ If implemented with a dynamic array:
                            - ⬜️ Given ,
                                - ⬜️ Push element:
	                                - $O(1)$
                                - ⬜️ Pop element: 
	                                - $O(1)$
                                - ⬜️ Peek (see element at top of stack): 
	                                - $O(1)$
                                - ⬜️ Access or modify element at arbitrary index: O(1)_O_(1)
                                - ⬜️ Check if element exists: O(n)_O_(_n_)
            - ⬜️ **Queue**
                - ⬜️ Queue operations are dependent on their implementation. A queue is only required to support dequeue and enqueue. If implemented with a doubly linked list:
                    - ⬜️ Given ,
                        - ⬜️ Enqueue element: 
                            - ⬜️ $$O(1)$$
                        - ⬜️ Dequeue element: 
                            - ⬜️ $$O(1)$$
                        - ⬜️ Peek (see element at front of queue): 
                            - ⬜️ $$O(1)$$
                        - ⬜️ Access or modify element at arbitrary index: 
                            - ⬜️ $$O(n)$$
                        - ⬜️ Check if element exists: 
                            - ⬜️ $$O(n)$$
                    - ⬜️ **Note:**
                        - ⬜️ most programming languages implement queues in a more sophisticated manner than a simple doubly linked list.
                        - ⬜️ Depending on implementation, accessing elements by index may be faster than $$O(n)$$, or $$O(n)$$ but with a significant constant divisor.
            - ⬜️ **Binary tree problems (DFS/BFS)**
                - ⬜️ Given n as the number of nodes in the tree,
                - ⬜️ Most algorithms will run in $$O(n⋅k)$$ time, where $$k$$ is the work done at each node, usually $$O(1)$$.
                    - ⬜️ This is just a general rule and not always the case.
                    - ⬜️ We are assuming here that BFS is implemented with an efficient queue.
            - ⬜️ **Binary search tree**
                - ⬜️ Given $$n$$ as the number of nodes in the tree,
                    - ⬜️ Add or remove element: 
                        - ⬜️ $$O(n)$$ worst case, $$O(log⁡n)$$ average case
                    - ⬜️ Check if element exists: $$O(n)$$ worst case, $$O(log⁡n)$$ average case.
                - ⬜️ The average case is when the tree is well balanced - each depth is close to full.
                    - ⬜️ The worst case is when the tree is just a straight line.
            - ⬜️ **Heap/Priority Queue**
                - ⬜️ Given  and talking about min heaps,
                    - ⬜️ Add an element:
                        - $$O(log⁡n)$$
                    - ⬜️ Delete the minimum element: 
                        - $$O(log⁡n)$$
                    - ⬜️ Find the minimum element: 
                        - $$O(1)$$
                    - ⬜️ Check if element exists: 
                        - $$O(n)$$
            - ⬜️ **Binary search**
                - Binary search runs in $$O(log⁡n)$$ in the worst case, where $$n$$ is the size of your initial search space.
            - ⬜️ **Miscellaneous**
                - ⬜️ Sorting: 
                    - ⬜️ $$O(n⋅log⁡n)$$, where $$n$$ is the size of the data being sorted
                - ⬜️ DFS and BFS on a graph: 
                    - ⬜️ $$O(n⋅k+e)$$, where $$n$$ is the number of nodes, $$e$$ is the number of edges, if each node is handled in $$O(1)$$ other than iterating over edges
                - ⬜️ DFS and BFS space complexity:
                    - ⬜️ typically $$O(n)$$, but if it's in a graph, might be $$O(n+e)$$ to store the graph
                - ⬜️ Dynamic programming time complexity: 
                    - ⬜️ $$O(n⋅k)$$, where $$n$$ is the number of states and $$k$$ is the work done at each state
                - ⬜️ Dynamic programming space complexity: 
                    - ⬜️ $$O(n)$$, where $$n$$ is the number of states
    - ⬜️ Reasonable complexities given input sizes
        - ### ⬜️ Input sizes vs time complexity
            
            - ⬜️ The constraints of a problem can be considered as hints because they indicate an upper bound on what your solution's time complexity should be.
                - ⬜️ Being able to figure out the expected time complexity of a solution given the input size is a valuable skill to have.
                - ⬜️ In all LeetCode problems and most online assessments (OA), you will be given the problem's constraints.
                - ⬜️ Unfortunately, you will usually not be explicitly told the constraints of a problem in an interview, but it's still good for practicing on LeetCode and completing OAs.
                - ⬜️ Still, in an interview, it usually doesn't hurt to ask about the expected input sizes.
            - ⬜️ **n <= 10**
                - ⬜️ The expected time complexity likely has a factorial or an exponential with a base larger than $$2 - O(n^2⋅n!)$$ or $$O(4^n)$$ for example.
                - ⬜️ You should think about backtracking or any brute-force-esque recursive algorithm.  is extremely small and usually **any** algorithm that correctly finds the answer will be fast enough.
            - ⬜️ **10 < n <= 20**
                - ⬜️ The expected time complexity likely involves $$O(2^n)$$.
                    - ⬜️ Any higher base or a factorial will be too slow ($$3^20 $$ = ~3.5 billion, and $$20!$$ is much larger).
                    - ⬜️ A $$2^n$$ usually implies that given a collection of elements, you are considering all subsets/subsequences - for each element, there are two choices:
                        - ⬜️ take it or don't take it.
                - ⬜️ Again, this bound is very small, so most algorithms that are correct will probably be fast enough. Consider backtracking and recursion.
            - ⬜️ **20 < n <= 100**
                - ⬜️ At this point, exponentials will be too slow. The upper bound will likely involve O(n3)_O_(_n_3).
                - ⬜️ Problems marked as "easy" on LeetCode usually have this bound, which can be deceiving. There may be solutions that run in O(n)_O_(_n_), but the small bound allows brute force solutions to pass (finding the linear time solution might not be considered as "easy").
                - ⬜️ Consider brute force solutions that involve nested loops. If you come up with a brute force solution, try analyzing the algorithm to find what steps are "slow", and try to improve on those steps using tools like hash maps or heaps.
            - ⬜️ **100 < n <= 1,000**
                - ⬜️ In this range, a quadratic time complexity O(n2)_O_(_n_2) should be sufficient, as long as the constant factor isn't too large.
                - ⬜️ Similar to the previous range, you should consider nested loops. The difference between this range and the previous one is that O(n2)_O_(_n_2) is usually the expected/optimal time complexity in this range, and it might not be possible to improve.
            - ⬜️ **1,000 < n < 100,000**
                - ⬜️ $$n<=105$$ is the most common constraint you will see on LeetCode. In this range, the slowest acceptable **common** time complexity is $$O(n⋅log⁡n)$$, although a linear time approach O(n) is commonly the goal.
                - ⬜️ In this range, ask yourself if sorting the input or using a heap can be helpful. If not, then aim for an O(n) algorithm.
                    - ⬜️ Nested loops that run in $$O(n^2)$$ are unacceptable - you will probably need to make use of a technique learned in this course to simulate a nested loop's behavior in $$O(1)$$ or $$O(log⁡n)$$:
                        - ⬜️ Hash map
                        - ⬜️ A two pointers implementation like sliding window
                        - ⬜️ Monotonic stack
                        - ⬜️ Binary search
                        - ⬜️ Heap
                        - ⬜️ A combination of any of the above
                - ⬜️ If you have an $$O(n)$$ algorithm, the constant factor can be reasonably large (around 40).
                    - One common theme for string problems involves looping over the characters of the alphabet at each iteration resulting in a time complexity of $$O(26n)$$.
            - ⬜️ **100,000 < n < 1,000,000**
                - ⬜️ $$n<=10^6$$ is a rare constraint, and will likely require a time complexity of $$O(n)$$.
                    - ⬜️ In this range, $$O(n⋅log⁡n)$$ is usually safe as long as it has a small constant factor.
                    - ⬜️ You will very likely need to incorporate a hash map in some way.
            - ⬜️ **1,000,000 < n**
                - ⬜️ With huge inputs, typically in the range of $$10^9$$ or more, the most common acceptable time complexity will be logarithmic $$O(log⁡n)$$ or constant $$O(1)$$.
                    - ⬜️ In these problems, you must either significantly reduce your search space at each iteration (usually binary search) or use clever tricks to find information in constant time (like with math or a clever use of hash maps).
                        - ⬜️ Other time complexities are possible like O(n), but this is very rare and will usually only be seen in very advanced problems.
    - ### ⬜️ Sorting algorithms
        
        - ⬜️ All major programming languages have a built-in method for sorting.
            - ⬜️ It is usually correct to assume and say sorting costs $$O(n⋅log⁡n)$$, where $$n$$ is the number of elements being sorted.
            - ⬜️ For completeness, here is a chart that lists many common sorting algorithms and their completeness.
            - ⬜️ The algorithm implemented by a programming language varies; for example, Python uses Timsort but in C++, the specific algorithm is not mandated and varies.
        - ⬜️ ![](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/713/interviews-and-tools/Figures/DSA/Chapter_11/sorting.png "sorting algorithm complexities") 
        - ⬜️ Definition of a stable sort from [Wikipedia](https://en.wikipedia.org/wiki/Category:Stable_sorts):
            - ⬜️ "Stable sorting algorithms maintain the relative order of records with equal keys (i.e. values). That is, a sorting algorithm is stable if whenever there are two records R and S with the same key and with R appearing before S in the original list, R will appear before S in the sorted list."
- ### ⬜️ General DS/A flowchart (when to use each DS/A)
    
    - ✅ Here's a flowchart that can help you figure out which data structure or algorithm should be used.
        - ✅ Note that this flowchart is very general as it would be impossible to cover every single scenario.
    - ⬜️ Note that this flowchart only covers methods taught in LICC, and as such more advanced algorithms like Dijkstra's is excluded.
        - ![](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/713/interviews-and-tools/Figures/DSA/Chapter_11/flowchart.png "data structures and algorithm flowchart")
- ### ⬜️ Interview stages cheat sheet
    
    - ⬜️ The following will be a summary of the "Stages of an interview" article. If you have a remote interview, you can print this condensed version and keep it in front of you during the interview.
    - ⬜️ **Stage 1: Introductions**
        - ⬜️ Have a rehearsed 30-60 second introduction regarding your education, work experience, and interests prepared.
            
        - ⬜️ Smile and speak with confidence.
        - ⬜️ Pay attention when the interviewer talks about themselves and incorporate their work into your questions later.
    - ⬜️ **Stage 2: Problem statement**
        - ⬜️ Paraphrase the problem back to the interviewer after they have read it to you.
        - ⬜️ Ask clarifying questions about the input such as the expected input size, edge cases, and invalid inputs.
        - ⬜️ Quickly walk through an example test case to confirm you understand the problem.
    - ⬜️ **Stage 3: Brainstorming DS&A**
        - ⬜️ Always be thinking out loud.
        - ⬜️ Break the problem down: figure out what you need to do, and think about what data structure or algorithm can accomplish it with a good time complexity.
        - ⬜️ Be receptive to any comments or feedback from the interviewer, they are probably trying to hint you towards the correct solution.
        - ⬜️ Once you have an idea, before coding, explain your idea to the interviewer and make sure they understand and agree that it is a reasonable approach.
    - ⬜️ **Stage 4: Implementation**
        - ⬜️ Explain your decision-making as you implement. When you declare things like sets, explain what the purpose is.
        - ⬜️ Write clean code that conforms to your programming language's conventions.
        - ⬜️ Avoid writing duplicate code - use a helper function or for loop if you are writing similar code multiple times.
        - ⬜️ If you are stuck, don't panic - communicate your concerns with your interviewer.
        - ⬜️ Don't be scared to start with a brute force solution (while acknowledging that it is brute force), then improve it by optimizing the "slow" parts.
        - ⬜️ Keep thinking out loud and talk with your interviewer. It makes it easier for them to give you hints.
    - ⬜️ **Stage 5: Testing & debugging**
        - ⬜️ When walking through test cases, keep track of the variables by writing at the bottom of the file, and continuously update them. Condense trivial parts like creating a prefix sum to save time.
        - ⬜️ If there are errors and the environment supports running code, put print statements in your algorithm and walk through a small test case, comparing the expected value of variables and the actual values.
        - ⬜️ Be vocal and keep talking with your interviewer if you run into any problems.
    - ⬜️ **Stage 6: Explanations and follow-ups**
        - ⬜️ Questions you should be prepared to answer:
            - ⬜️ Time and space complexity, average and worst case.
            - ⬜️ Why did you choose this data structure, algorithm, or logic?
            - ⬜️ Do you think the algorithm could be improved in terms of complexity? If they ask you this, then the answer is _usually_ yes, especially if your algorithm is slower than O(n)_O_(_n_).
    - ⬜️ **Stage 7: Outro**
        - ⬜️ Have questions regarding the company prepared.
        - ⬜️ Be interested, smile, and ask follow-up questions to your interviewer's responses.
- ## ⬜️ Topics
	- ### ⬜️ Arrays and Strings
		- ### ⬜️ INTRODUCTION
			- In terms of algorithm problems, arrays (1D) and strings are very similar: they both represent an ordered group of elements. Most algorithm problems will include either an array or string as part of the input, so it's important to be comfortable with the basic operations and to learn the most common patterns.
			- "Array" can mean something different between languages. For example, Python primarily uses "lists" instead of arrays which are extremely lenient. Initialization is as easy as `arr = []`, and you don't need to worry about the type of data you store in the list or the size of the list. Other languages like C++ require you to specify the size and data type of the array during initialization, but also have support for lists (like `std::vector` in C++).
				- """Technically, an array can't be resized. A dynamic array, or list, can be. In the context of algorithm problems, usually when people talk about arrays, they are referring to dynamic arrays. **In this entire course, we will be talking about dynamic arrays/lists, but we will just use the word "array".** """
	
			- Similarly, strings are implemented differently between languages. In Python and Java, they are immutable. In C++, they are mutable. It's important to know the details behind arrays and strings for the language you plan on using in interviews. We don't have time to go through all the different implementations for each language, so please research it for your chosen language if you aren't already familiar.
				- """Mutable: a type of data that can be changed. Immutable: A type of data that cannot be changed. If you want to change something immutable, you will need to recreate the entire thing."""
			- Why should we care about something being mutable or immutable? Imagine you have a mutable array `arr = ["a", "b", "c"]` and an immutable string `s = "abc"`, and you want to change the `c` into a `d`. You can easily do `arr[2] = "d"`, but you cannot do `s[2] = "d"`. As such, if you wanted the string `s = "abd"`, you would need to create it entirely from scratch. With such a small string, it's not a big deal. But sometimes you are dealing with strings with 100,000 characters, so creating new versions just to modify one character is very expensive (O(n)O(n), where nn is the size of the string).
			- As mentioned before, a majority of algorithm problems will involve an array or string. They are extremely versatile data structures and it's impossible to list all the relevant problem-solving techniques in one article. In the next few articles, we'll go over the most common techniques. But first, let's take a quick look at the time complexity of array and string operations.
			- ![time complexity chart for arrays and strings](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/703/arraystrings/Figures/DSA/Chapter_1/1_1.png)
			- Appending to the end of a list is [amortized O(1)](https://stackoverflow.com/questions/33044883/why-is-the-time-complexity-of-pythons-list-append-method-o1).
		- #### ⬜️ Two pointers
			- ✅ Two pointers is an extremely common technique used to solve array and string problems. 
				- ✅ It involves having two integer variables that both move along an iterable. 
				- ✅ In this article, we are focusing on arrays and strings. 
				- ✅ This means we will have two integers, usually named something like `i` and `j`, or `left` and `right` which each represent an index of the array or string.
			- ✅ There are several ways to implement two pointers.
			- ⬜️ To start, let's look at the following method:
				- ❤️ Start the pointers at the edges of the input. 
				- ❤️ Move them towards each other until they meet.
			- ✅ Converting this idea into instructions:
				1. ✅ Start one pointer at the first index `0` and the other pointer at the last index `input.length - 1`.
				2. ✅ Use a while loop until the pointers are equal to each other.
				3. ✅ At each iteration of the loop, move the pointers towards each other. 
					- ✅ This means either increment the pointer that started at the first index, decrement the pointer that started at the last index, or both. 
					- ✅ Deciding which pointers to move will depend on the problem we are trying to solve.
			- ✅ Here's some pseudocode illustrating the concept:
					```function fn(arr):
						left = 0
					    right = arr.length - 1
					
					    while left < right:
					        Do some logic here depending on the problem
					        Do some more logic to decide one of the following:
					            1. left++
					            2. right--
					            3. Both left++ and right--
					```
			- ✅ The strength of this technique is that 
				- ✅ we will never have more than O(n) iterations for the while loop because 
					- ✅ the pointers start n away from each other and 
					- ✅ move at least one step closer in every iteration. 
			- ✅ Therefore, if we can keep the work inside each iteration at O(1), this technique will result in 
				- ✅ a linear runtime, which is usually the best possible runtime. 
			- Let's look at some examples.
				- ✅ Example 1: 
					- ✅ ```Given a string `s`, return `true` if it is a palindrome, `false` otherwise. A string is a palindrome if it reads the same forward as backward. That means, after reversing it, it is still the same string. For example: "abcdcba", or "racecar".```
					- ✅ After reversing a string, 
						- ✅ the first character becomes the last character. 
						- ✅ If a string is the same after being reversed, that means 
							- ✅ the first character is the same as the last character, 
							- ✅ the second character is the same as the second last character, and 
							- ✅ so on. 
						- ✅ We can use the two pointers technique here to check that all corresponding characters are equal. 
						- ✅ To start, we check the first and last characters using two separate pointers. 
						- ✅ To check the next pair of characters, we just need to move our pointers toward each other one position. 
						- ✅ We continue until the pointers meet each other or we find a mismatch.
					- **Click here for a more detailed explanation if needed**
						- ⬜️ We keep track of two indices: 
							- ⬜️ a left one, and a right one. 
							- ⬜️ In the beginning, the left index points to the first character, and the right index points to the last character. 
							- ⬜️ If these characters are not equal to each other, we know the string can't be a palindrome, so we return false. 
							- ⬜️ Otherwise, the string may be a palindrome; we need to check the next pair. 
							- ⬜️ To move on to the next pair, we move the left index forward by one, and the right index backward by one. 
							- ⬜️ Again, we check if the pair of characters are equal, and if they aren't, we return false.
						- ⬜️ We continue this process until we either find a mismatch (in which case the string cannot be a palindrome, so we return false), or the pointers meet each other (which indicates we have gone through the entire string, checking all pairs). 
							- ⬜️ If we get through all pairs without a mismatch, we know the string is a palindrome, so we can return true.
					- ⬜️ To run the algorithm until the pointers meet each other, we can use a while loop. 
						- ⬜️ Each iteration in the while loop checks one pair. 
						- ⬜️ If the check is successful, we increment `left` and decrement `right` to move to the next pair. 
						- ⬜️ If the check is unsuccessful, we return false.
					- ⬜️Notice that if the input was an array of characters instead of a string, the algorithm wouldn't change. 
						- ⬜️The two pointers technique works as long as the index variables are moving along some abstract iterable.
					- ⬜️ This algorithm is very efficient as not only does it run in $O(n)$, but it also uses only $O(1)$ space. 
						- ⬜️No matter how big the input is, we always only use two integer variables. 
						- ⬜️ The time complexity is $O(n)$ because the while loop iterations cost $O(1)$ each, and there can never be more than $O(n)$ iterations of the while loop - the pointers start at a distance of $n$ from each other and move closer by one step each iteration.
				- ⬜️ Example 2: 
					- ⬜️ Given a **sorted** array of unique integers and a target integer, return `true` if there exists a pair of numbers that sum to target, `false` otherwise. 
						- ⬜️ This problem is similar to [Two Sum](https://leetcode.com/problems/two-sum/). 
						- ⬜️ (In Two Sum, the input is not sorted).
					- ⬜️ For example, given `nums = [1, 2, 4, 6, 8, 9, 14, 15]` and `target = 13`, return true because `4 + 9 = 13`.
					- ⬜️ Note: 
						- ⬜️ a similar version of this problem can be found on LeetCode: [167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)
					- ⬜️ The brute force solution would be to iterate over all pairs of integers.
						- ⬜️ Each number in the array can be paired with another number, so this would result in a time complexity of $O(n^2)$, where $n$ is the length of the array. 
						- ⬜️ Because the array is sorted, we can use two pointers to improve to an $O(n)$ time complexity.
					- ⬜️Let's use the example input. 
						- ⬜️With two pointers, we start by looking at the first and last numbers. 
						- ⬜️ Their sum is `1 + 15 = 16`. Because `16 > target`, we need to make our current sum smaller. 
						- ⬜️ Therefore, we should move the `right` pointer. 
						- ⬜️ Now, we have `1 + 14 = 15`. 
						- ⬜️ Again, move the right pointer because the sum is too large. 
						- ⬜️ Now, `1 + 9 = 10`. Since the sum is too small, we need to make it bigger, which can be done by moving the `left` pointer. 
						- ⬜️ `2 + 9 = 11 < target`, so move it again. 
						- ⬜️ Finally, `4 + 9 = 13 = target`.
					- ⬜️ The reason this algorithm works: 
						- ⬜️ because the numbers are sorted, moving the left pointer permanently increases the value the left pointer points to (`nums[left] = x`). 
						- ⬜️ Similarly, moving the right pointer permanently decreases the value the right pointer points to (`nums[right] = y`). 
						- ⬜️ If we have `x + y > target`, then we can never have a solution with `y` because `x` can only increase. 
						- ⬜️ So if a solution exists, we can only find it by decreasing `y`. 
						- ⬜️ The same logic can be applied to `x` if `x + y < target`.
				- ⬜️  **Click here for a more detailed explanation if needed**
					- ⬜️  Let's say we have `nums = [3, 6, 21, 23, 25]` and `target = 27`. 
						- ⬜️ We need to pick two numbers that sum to `target`. 
						- ⬜️ Using the two pointers technique, we start with the first and last numbers. 
						- ⬜️ Because the input is sorted, this is the smallest and largest number. 
						- ⬜️ We have `3 + 25 = 28`, which is greater than `target`.
					- ⬜️ Let's look at the `25`. 
						- ⬜️ We paired this number with the smallest number, and the sum was **still** too large. 
						- ⬜️ That implies that the `25` could never be part of the answer because if we chose any number other than the `3` to pair it with, the sum would be even larger. 
						- ⬜️ Since it can't be part of the answer, we move on to the next largest number, which is `23`.
					- ⬜️  Now, we have `3 + 23 = 26`. This is smaller than `target`. In the previous step, we determined that the `25` could never be part of the answer. This makes the `23` the new "largest" number. Despite pairing the `3` with the largest number, the sum is **still** too small. This implies that the `3` could never be part of the answer because if we chose any of the other remaining numbers (the `6` or `21`), the sum would be even smaller. Since it can't be part of the answer, we move on to the next smallest number, which is `6`.
					- ⬜️ Now, we have `6 + 23 = 29`. Once again, our sum is too large. We apply the same logic as before - the `23` could never be part of the answer because we are already pairing it with the smallest number (that we haven't already ruled out), yet the sum is still too large. So we move to the next largest number, which is the `21`.
					- ⬜️ Finally, we have `6 + 21 = 27`, and we have found our target.
					- ⬜️ To implement this algorithm, we use a similar process as in the previous palindrome example. We use a while loop until the pointers meet each other. If at any point the sum is equal to the `target`, we can return true. If the pointers meet each other, it means we went through the entire input without finding `target`, so we return false.
					- ⬜️ Like in the previous example, this algorithm uses $O(1)$ space and has a time complexity of $O(n)$.
### ⬜️ Another way to use two pointers

This method where we start the pointers at the first and last indices and move them towards each other is only one way to implement two pointers. Algorithms are beautiful because of how abstract they are - "two pointers" is just an idea, and it can be implemented in many different ways. Let's look at another method and some new examples. The following method is applicable when the problem has two iterables in the input, for example, two arrays.

> Move along both inputs simultaneously until all elements have been checked.

Converting this idea into instructions:

1. Create two pointers, one for each iterable. Each pointer should start at the first index.
2. Use a while loop until one of the pointers reaches the end of its iterable.
3. At each iteration of the loop, move the pointers forward. This means incrementing either one of the pointers or both of the pointers. Deciding which pointers to move will depend on the problem we are trying to solve.
4. Because our while loop will stop when one of the pointers reaches the end, the other pointer will not be at the end of its respective iterable when the loop finishes. Sometimes, we need to iterate through all elements - if this is the case, you will need to write extra code here to make sure both iterables are exhausted.

Here's some pseudocode illustrating the concept:

function fn(arr1, arr2):
    i = j = 0
    while i < arr1.length AND j < arr2.length:
        Do some logic here depending on the problem
        Do some more logic here to decide on one of the following:
            1. i++
            2. j++
            3. Both i++ and j++

    // Step 4: make sure both iterables are exhausted
    // Note that only one of these loops would run
    while i < arr1.length:
        Do some logic here depending on the problem
        i++

    while j < arr2.length:
        Do some logic here depending on the problem
        j++

Similar to the first method we looked at, this method will have a linear time complexity of O(n+m)O(n+m) if the work inside the while loop is O(1)O(1), where `n = arr1.length` and `m = arr2.length`. This is because at every iteration, we move at least one pointer forward, and the pointers cannot be moved forward more than `n + m` times without the arrays being exhausted. Let's look at some examples.

---

> Example 3: Given two sorted integer arrays `arr1` and `arr2`, return a new array that combines both of them and is also sorted.

The trivial approach would be to first combine both input arrays and then perform a sort. If we have `n = arr1.length + arr2.length`, then this gives a time complexity of O(n⋅log⁡n)O(n⋅logn) (the cost of sorting). This would be a good approach if the input arrays were not sorted, but because they are sorted, we can take advantage of the two pointers technique to improve to O(n)O(n).

> In the previous example, we declared `n = arr1.length` and `m = arr2.length`. Here, we are saying `n = arr1.length + arr2.length`. Why have we changed the definition? Remember that when it comes to big O, **we are allowed to define the variables as we see fit**. We could certainly stick to using `n, m`. In that case, the time complexity of the sorting approach would be O((n+m)⋅log⁡(m+n))O((n+m)⋅log(m+n)) and the time complexity of the approach we are about to cover would be O(n+m)O(n+m). It makes no difference either way, but one justification we could give here is that since we are combining the arrays, the total length is a significant number, so it makes sense to represent it as `n`.
> 
> Keeping the definition as `n = arr1.length` and `m = arr2.length` is fine as well.

We can build the answer array `ans` one element at a time. Start two pointers at the first index of each array, and compare their elements. At each iteration, we have 2 values. Whichever value is lower needs to come first in the answer, so add it to the answer and move the respective pointer.

**Click here for a more detailed explanation if needed**

Sorting an array of length nn costs O(n⋅log⁡n)O(n⋅logn). We can improve the time complexity by a factor of log⁡nlogn by taking advantage of the input arrays already being sorted.

If we start with the smallest number from each array, then whichever one is smaller **must** be before the other one - so we add it to the answer and move to the next number in that array. If the values are equal, it doesn't matter which one we choose - we can arbitrarily choose either. This process can be repeated until one of the arrays runs out of numbers.

When this happens, we are still left with some numbers in the other array. These numbers are all larger than the largest number in the exhausted array. We should just append them to the answer.

  

Like in the previous two examples, this algorithm has a time complexity of O(n)O(n) and uses O(1)O(1) space (if we don't count the output as extra space, which we usually don't).

---

> Example 4: [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/).
> 
> Given two strings `s` and `t`, return `true` if `s` is a subsequence of `t`, or `false` otherwise.
> 
> A subsequence of a string is a sequence of characters that can be obtained by deleting some (or none) of the characters from the original string, while maintaining the relative order of the remaining characters. For example, "ace" is a subsequence of "abcde" while "aec" is not.

In this problem, we need to check if the characters of `s` appear in the same order in `t`, with gaps allowed. For example, `"ace"` is a subsequence of `"abcde"` because `"abcde"` contains the letters `"ace"` in that same order - the fact that they aren't consecutive doesn't matter.

We can use two pointers to solve this in linear time. If we find that `s[i] == t[j]`, that means we "found" the letter at position `i` for `s`, and we can move on to the next one by incrementing `i`. We should increment `j` at each iteration no matter what (which means we could also implement this algorithm using a for loop). `s` is a subsequence of `t` if we can "find" all the letters of `s`, which means that `i == s.length` at the end of the algorithm.

**Click here for a more detailed explanation if needed**

For every character in `s`, we need to find a match in `t`. Let's say we have `s = "bc"` and `t = "abcd"`. Using the two pointers technique, we start by looking at the first character in both strings.

We need to try and match the first character of `s`, which is `"b"`. The first character of `t` is `"a"`, which is not a match. As such, we will move to the next character in `t`. We don't move forward in `s` just yet, because we still need to match the `"b"`. The next character of `t` is `"b"`, and we have found a match. Now, we can move on to the next character in `s`, which is the `"c"`. A character in `t` can only be matched once, so we must also move forward in `t`. Now, we have another match since the next character in `t` is also `"c"`.

We have managed to match all the characters in `s`, which means that `s` is a subsequence of `t`.

As you can see, in both scenarios (match or mismatch), we move forward in `t`. In the match scenario, it's because we can't use a letter in `t` multiple times. In the mismatch scenario, it's like we're discarding the character since it's not useful. We only move forward in `s` when we find a match, since our task is to match all characters in `s`.

  

Just like all the prior examples, this solution uses O(1)O(1) space. The time complexity is linear with the lengths of `s` and `t`.

---

### Closing notes

Remember that the methods laid out here are just guidelines. For example, in the first method, we started the pointers at the first and last index, but sometimes you might find a problem that involves starting the pointers at different indices. In the second method, we moved two pointers forward along two different inputs. Sometimes, there will only be one input array/string, but we still initialize both pointers at the first index and move both of them forward.

Two pointers just refers to using two integer variables to move along some iterables. The strategies we looked at in this article are the most common patterns, but always be on the lookout for a different way to approach a problem. There are even problems that make use of "three pointers".

> The chapters and articles in this course are ordered in a way that ideas learned in earlier chapters can be applied to later chapters. Two pointers certainly has a lot more applications than just what is in this article - don't worry, this won't be the last we'll be seeing of it.

Before we move on to the next pattern, try the upcoming practice problems to apply what was learnt here. The practice problems are the next item in the course - you can use the "Next" button at the top of your screen, or access the problems on the left side menu.