# Node Class
## Java
    class Node {
      public value;
      private Vector _connectedNodes;
      
      public Node() {
        value = 0;
      }
      public fire() {
        value++;
        foreach(Node n in _connectedNodes) {
          n.fire();
        }
      }
      pubilc addOutput(Node n) {
        _connectedNodes.addElement(n);
      }
    }
