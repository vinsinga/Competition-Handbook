# Node Class
## Java - Detailed
    // Defines a node object that can be used to build a compute neural net.
    class Node {
      // Stores how many times the network has been triggered.
      public value;
      // Stores pointers to other nodes that should be fired when this node is fired.
      private Vector _connectedNodes;
      
      // Default constructor.
      public Node() {
        // Initialize the int variable value.
        value = 0;
        // Initialize the vector struct.
        _connectedNodes = new Vector();
      }
      // Fires the node by incrementing the value struct and triggering all connected Node objects.
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
## Java - Minified
    class Node {
      public v;
      private Vector cn;
      public Node() {
        v = 0;
        cn = new Vector();
      }
      public fire() {
        v++;
        foreach(Node n in cn) {
          n.fire();
        }
      }
      pubilc addNode(Node n) {
        cn.addElement(n);
      }
    }
