# Optimization - Travelling Salesman Problem

## Links to source code:

- [Brute force](https://github.com/piotrdurniat/tsp-brute-force)
- [Dynamic Programming (Held-Karp Algorithm)](https://github.com/piotrdurniat/tsp-held-karp)
- [Branch and Bound](https://github.com/piotrdurniat/tsp-branch-and-bound)
- [Simulated Annealing](https://github.com/piotrdurniat/tsp-simulated-annealing)
- [Genetic Algorithm](https://github.com/piotrdurniat/tsp-genetic-algorithm)

# Comparison of Exact Algorithms

Comparison of Brute Force, Branch and Bound, and Held-Karp algorithms.

## Time Comparison

The graph below shows the relationship between the algorithm's running time [ns] and the number of vertices in the graph. It includes results for the Brute Force, Branch and Bound, and Held-Karp algorithms. Additionally, an $n!$ curve is superimposed for complexity comparison.

![Relationship between the execution time of the studied algorithms and the number of graph vertices. Logarithmic scale.](img/graph-comp-time.png)

_Figure: Relationship between the execution time of the studied algorithms and the number of graph vertices. Logarithmic scale._

## Memory Usage Comparison

Below is a graph showing the relationship between memory usage and the number of vertices in the graph for the Branch and Bound and Held-Karp algorithms.

![Relationship between the memory usage of the studied algorithms and the number of graph vertices. Logarithmic scale.](img/graph-comp-ram.png)

_Figure: Relationship between the memory usage of the studied algorithms and the number of graph vertices. Logarithmic scale._

# Comparison of Heuristic Algorithms

Comparison of the Simulated Annealing algorithm and the Genetic algorithm.

## Average Error Results for Final Parameter Selection of Algorithms

### Genetic Algorithm

![Error magnitude relative to instances for final parameters of the genetic algorithm.](img/genetic/final-params-error.png)

_Figure: Error magnitude relative to instances for final parameters of the genetic algorithm._

### Simulated Annealing Algorithm

![Error magnitude for different instances for final parameters.](img/sa/final-graph.png)

_Figure: Error magnitude for different instances for final parameters of the simulated annealing algorithm._

# Results Analysis

## Exact Algorithms

Among the studied exact algorithms, the Brute Force algorithm has the highest time complexity ($O(n!)$), while the Held-Karp algorithm has the lowest time complexity ($O(n^2\cdot 2^{n-1})$).
The memory complexity of the Brute Force algorithm has not been studied in this experiment. The Held-Karp algorithm has lower memory complexity ($O(n\cdot 2^{n})$) than the Branch and Bound algorithm.

## Heuristic Algorithms

Due to varying termination conditions and different instances tested, directly comparing the genetic and simulated annealing algorithms for error rate or speed is challenging. With an acceptable error threshold of 150% and a time limit of 5 minutes, the genetic algorithm can address problems with up to 1000 vertices. Conversely, with a 30% error margin and a 30-second time constraint, the simulated annealing algorithm is effective for instances up to approximately 300 vertices.

# Conclusions

## Exact Algorithms

Exact algorithms guarantee the finding of the global optimum of the function. Their execution time is strictly dependent on the size of the instance, so it is possible to measure their time complexity and memory complexity.

Since the execution time or memory usage grows exponentially, assuming that the limit on execution time is $\approx 10 min$, and memory usage is $\approx 12 GB$, these algorithms can only be used for small instances (up to 30 vertices).

## Heuristic Algorithms

Heuristic algorithms offer a trade-off between execution time and solution accuracy without guaranteeing an optimal solution. Their performance and termination conditions can be tailored through empirical testing to balance between speed and accuracy for various problems. This customization process involves adjusting algorithm parameters based on the problem's specific characteristics, such as the number of vertices or edge weights. While effective for large instances where exact algorithms are impractical due to computational constraints, heuristic methods require thorough testing to identify satisfactory parameter settings, which can be time-consuming. For small instances (≤ 30 vertices), heuristic algorithms can potentially match the performance of exact algorithms but without certainty of achieving the global optimum for every case. Thus, while exact algorithms are preferred for smaller problems due to their precision, heuristic algorithms are better suited for larger problems, offering flexibility and scalability.
