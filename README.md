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

Asymtotic analysis can be misleading in practice
- The way you derive a recursive relation to get asymtotic complexity can vary widely in performance times even if asymtotically they are the same. say $1000n^2+n+3$ is your relation, compared to $2n^2+1$. Asymtotically, they are the exact same however, $2n^2+1$ is faster by multiple orders of magnitude in practice
- Asymtotic analysis only takes into account that the size of an input is the only thing that matters in runtime. So anything hardware related that could potentially change expected runtime is not accounted for
- Sometimes, an algorithmn that is worse asymtotically is faster for your current use-case for smaller input sizes. Take $4n$ and $205log(n)$ asymtotically, $205log(n)$ is better but under smaller inputs, $4n$ is better up to about 100 elements.

Assuming it took 5 seconds to go through a binary search tree with 1000 elements, it would take about 6 seconds for 10000 elements as a binary search tree has an average case of $\Theta(log(n))$

$log(1000)+2 = 5$ seconds therefore $log(10000)+2 = 6$ seconds

Getting 100 seconds after running 10000 elements
- This could be a case of during the 1000 search, the thing you were looking for was at the very top while during 10000 searches, it was at the very bottom worst case.
- There could have been some hardware issue that was not accounted for which would increase the runtime.
- The binary search tree could contain multiple different data types which would end up slowing down the runtime.



