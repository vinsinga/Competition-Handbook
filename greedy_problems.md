# Greedy Problems

### 1. Define G
Graph $$G$$ is composed of two arrays/lists $$V,E$$. $$G$$ is formally denoted as $$G=(V,E)$$ $$V$$ is a list of all nodes in a graph (e.g. $$[1,2,3,...,n]$$). E is a list of all edges defined within a graph. For example, if you have a line going from node 2 to node three, your $$E$$ array would look like $$[[2,3],...,[n1,n2]]$$.

### 2. Permutate $$V$$
Since no algebraic formula exists for solving coloring/matching problems, we must brute force all possible inputs of $$V$$. The method for this varies by language.

Python:
```python
n_list = [1,2,3,4]
permutes = itertools.permutations(n_list)
```