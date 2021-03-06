# Node Class

## Detailed Class Declaration

``` Java
// Defines a node object that can be used to build a compute neural net.
class Node {
    // Stores how many times the network has been triggered.
    public int value;
    // Stores pointers to other nodes that should be fired when this
    // node is fired.
    private ArrayList<Node> _connectedNodes;

    // Default constructor.
    public Node() {
        // Initialize the int variable value.
        value = 0;
        // Initialize the vector struct.
        _connectedNodes = new ArrayList();
    }
    // Fires the node by incrementing the value struct and
    // triggering all connected Node objects.
    public fire() {
        // Increment the value variable.
        value++;
        // Loop through all connected nodes and fire them.
        foreach(Node n in _connectedNodes) {
            n.fire();
        }
    }
    // Adds a node to the output of the current node when fired.
    pubilc addOutput(Node n) {
        // Add argument to the initialized Vector struct.
        _connectedNodes.addElement(n);
    }
}
```

## Minified Class Declaration

``` Java
class Node {
    public int v = 0;
    public ArrayList<Node> cn;
    public Node() {
        cn = new ArrayList();
    }
    public fire() {
        v++;
        foreach(Node n in cn) {
            n.fire();
        }
    }
}
```
To shorten the code, the `addOutput(Node)` function has been removed. To add a node to the list of reciever nodes, use `node1.cn.addElement(node2);` within your program.

# Usage of Node Class

## 1:1 Storage Model

``` Java
public someFunction(var args) {
    // Create the first node.
    Node n1 = new Node();
    // Create a second node.
    Node n2 = new Node();
    // Link the two nodes so n1 triggers n2.
    n1.addNode(n2);
    // Fire the tree.
    n1.fire();
    // Since this network map is not event-based,
    // function will only return once the entire tree has fired.
    // Check the values of each node.
    System.out.println("Node 1:\t" + n1.value);
    System.out.println("Node 2:\t" + n2.value);
}
```

The above code should output the following:

```
Node 1:    1
Node 2:    1
```

## ArrayList<> Storage Model

``` Java
public someFunction(var args) {
    // Create the first node.
    Node n1 = new Node();
    // Create a ArrayList<Node> object.
    ArrayList<Node> nodeList = new ArrayList();
    // Add the node to the list.
    nodeList.addElement(n1);
    // Create 9 nodes and link them together.
    for(int i = 0; i <= 9; i++) {
        Node n = new Node();
        n.cn.addElement(nodeList[i]);
        nodeList.addElement(n);
    }
    // Fire the tree twice.
    n1.fire();
    n1.fire();
    // Since this network map is not event-based, function will only return once
    the entire tree has fired.
    // Check the values of each node.
    System.out.println("Node 1:\t" + nodeList[0].value);
    System.out.println("Node 10:\t" + nodeList[9].value);
}
```

The above code should output the following:

```
Node 1:    2
Node 10:   2
```

## Search Patterns
### Breadth-First Search
To perform a breadth-first search, create a downward-facing fan with a single node at the top. Fire the top node then check the result by looking at the value of the nodes at the bottom.

This method is useful for problems that require analyzing the effect of one action on multiple variables.

### Depth-First Search
Unlike breadth-first, a depth-first search tree is an upward facing fan with several nodes at the top and one on the bottom. To run, fire some or all of the top nodes and look at the bottom node for the result.

This method works best on ANNs that are adapted for dynamic-fire weight (having a pulse value other than 1). Depth-First trees are best for problems that involve looking at the effect of multiple different input values to obtain a single value. This is similar to the function of actual ML neural networks.