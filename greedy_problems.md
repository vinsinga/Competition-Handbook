# Greedy Problems

### 1. Define $$G$$
Graph $$G$$ is composed of two arrays/lists $$V,E$$. $$G$$ is formally denoted as $$G=(V,E)$$. $$V$$ is a list of all nodes in a graph (e.g. $$[1,2,3,...,n]$$). E is a list of all edges defined within a graph. For example, if you have a line going from node 2 to node three, your $$E$$ array would look like $$[[2,3],...,[n1,n2]]$$.

### 2. Permutate $$V$$
Since no algebraic formula exists for solving coloring/matching problems, we must brute force all possible inputs of $$V$$. The method for this varies by language.

Python:
``` Python
n_list = [1,2,3,4]
permutes = itertools.permutations(n_list)
```

Java:
``` Java
List nList = new List([1,2,3,4]);

public List<List<E>> generatePerm(List<E> original) {
   if (original.size() == 0) { 
     List<List<E>> result = new ArrayList<List<E>>();
     result.add(new ArrayList<E>());
     return result;
   }
   E firstElement = original.remove(0);
   List<List<E>> returnValue = new ArrayList<List<E>>();
   List<List<E>> permutations = generatePerm(original);
   for (List<E> smallerPermutated : permutations) {
     for (int index=0; index <= smallerPermutated.size(); index++) {
       List<E> temp = new ArrayList<E>(smallerPermutated);
       temp.add(index, firstElement);
       returnValue.add(temp);
     }
   }
   return returnValue;
}
```
*Modified from http://stackoverflow.com/questions/10305153/generating-all-possible-permutations-of-a-list-recursively*

### Iterate and Solve
For every permutation of $$V$$, you now need to find the highest color $$c$$ in that configuration. If your algorithm is taking too long, you can try selecting a random sample of permutations and only testing those. This method may not work on large graphs or those with highly complex $$E$$ configurations.

Python:
``` Python
sums = []
for permutation in itertools.permutations(n_list):
  colors = [0] * (len(n_list) + 1)
  for node in permutation:
    color = 1
    c_collision = True
    while(c_collision):
      c_collision = False
      for edge in e_list:
        if node in edge:
          mod_edge = edge
          mod_edge.remove(node)
          if color == colors[mod_edge[0]]:
            c_collision = True
            color = color + 1
            break
    colors[node] = color
    sum = []
    sum.append(permutation)
    sum.append(max(colors))
# for [x,y] in sums[], min(y) is the smallest c with configuration x.
```

Java:
``` Java
ArrayList<Integer> sums = new ArrayList();
for (ArrayList<Integer> permutation : generatePerm(nList)) {
  ArrayList<Integer> colors = new ArrayList(Collections(nCopies(nList.length() + 1, 0)));
  for (int node : permutation) {
    int color = 1;
    boolean cCollision = true;
    while (cCollision) {
      cCollision = false;
      for (ArrayList<Integer> edge : eList) {
        if (edge.contains(node)) {
          mod_edge = edge;
          mod_edge.remove(node);
          if (color == colors[mod_edge[0]]) {
            cCollision = true;
            color++;
            break;
          }
        }
      }
    }
    colors[node] = color;
    sums.add(Collections.max(colors));
  }
}
// for x in sums<>[], Collections.min(sums) is the smallest c.
```

When possible, Python should be used as it is usually more tolerant to type conversion issues and has built-in support for working with collections (List objects).