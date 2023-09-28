[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11754416&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

Asymptotic analysis can be misleading in practice
- The way you derive a recursive relation to get asymptotic complexity can vary widely in performance times even if asymptotically they are the same. say $1000n^2+n+3$ is your relation, compared to $2n^2+1$. asymptotically, they are the exact same however, $2n^2+1$ is faster by multiple orders of magnitude in practice
- asymptotic analysis only takes into account that the size of an input is the only thing that matters in runtime. So anything hardware related that could potentially change expected runtime is not accounted for
- The bounds of Big O notation are loose. O(f(n)) needs to only grow at least as fast as T(n), so T(n) = n where O(n), $O(n^2)$, and $O(n^n)$ are valid for big O.

Assuming it took 5 seconds to go through a binary search tree with 1000 elements, it would take about 6.6 seconds for 10000 elements as a binary search tree has an average case of $\Theta(log(n))$

$\frac{\log_{2}\left(1000\right)}{2}$ is approximately 5 seconds therefore $\frac{\log_{2}\left(10000\right)}{2}$ is approximatly 6.6 seconds

Getting 100 seconds after running 10000 elements
- This could be a case of during the 1000 search, the thing you were looking for was at the very top while during 10000 searches, it was at the very bottom worst case.
- There could have been some hardware issue that was not accounted for which would increase the runtime.
- The binary search tree could contain multiple different data types which would end up slowing down the runtime.



