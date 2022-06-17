1. Describe how your prefetcher works.
My prefetcher is designed to throttle depending on how sucessful its prefetches are.

It starts with the same number that would be fed to the sequential prefetcher,
If more than 1% are misses, it halves the number prefetched, otherwise the number is doubled.
(I created another stats.misses that reset after each round of prefetching to keep track of the hit ratio)

The minimum number prefetched is set to 1
The maximum number prefetched is set to 50



2. Explain how you chose that prefetch strategy.
I found this strategy in the lecture linked below.
It sounded like it would work fairly well on pretty much all inputs, and I wanted to try it out


3. Discuss the pros and cons of your prefetch strategy.
It should work reasonably well on all inputs.
The main downside is that doubling/halving is probably too big of a change once the number to prefetch is fairly large.
It may be good to cap the amount the prefetch number can change by.
If you know a little more about the pattern of the memory accesses, the strategy could be tailored a lot better.


4. Demonstrate that the prefetcher could be implemented in hardware (this can be
   as simple as pointing to an existing hardware prefetcher using the strategy
   or a paper describing a hypothetical hardware prefetcher which implements
   your strategy).

See citation below (slide 39/40/41)

5. Cite any additional sources that you used to develop your prefetcher.
Carnegie Mellon University Lecture (Link below)
https://course.ece.cmu.edu/~ece740/f11/lib/exe/fetch.php?media=wiki:lectures:onur-740-fall11-lecture24-prefetching-afterlecture.pdf
