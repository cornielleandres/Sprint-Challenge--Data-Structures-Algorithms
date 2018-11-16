# Analysis of Algorithms - Answers
**Exercise I**:
*	a) `O(n^3)`: This is because the while loop will only stop after `a` has reached the value of `n^3`. That is to say, `n^3` iterations will be made.

*	b) `O(n^3)`: The outer-most loop(i-loop) will run through `n` times (we are at `O(n)` here). The next loop(j-loop) is nested inside, and will run through _on average_ `n/2` times for every iteration made in the previous i-loop (we are at `O(n * n/2) = O((n^2)/2) => O(n^2)` here). For the next nested loop(k-loop), its the same thing as for the j-loop; it wil on average iterate `n/2` times for every j-loop iteration (we are at `O(n^2 * n/2) = O((n^3)/2) => O(n^3)` here). For the last loop(l-loop), the value of k does not matter; it is effectively the same as `for (l = 1; l < 10; l++)`, which means it will make 9 iterations for every iteration made in the previous loop (we are finally at `O(n^3 * 9) = O(9n^3) => O(n^3)` here).

*	c) `O(n)`: Here, it will return a chain of 2's added up until `bunnies` reaches 0: `2 + 2 + 2 + ... + 0`. Since it will recursively call itself once for every bunny, the number of iterations will scale linearly with the number of bunnies.

**Exercise II**:
*	This can be done in `O(log(n))` time. You can achieve this by dropping an egg from half the height (starting at n/2). If the egg breaks, you know that `f >= n/2`; if it does not break, `f < n/2`. You can repeat this, every time halving the height, and get to the value of `f` on average in `O(log(n))` time, thus minimizing the number of dropped eggs.