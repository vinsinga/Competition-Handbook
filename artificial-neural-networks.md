# Artificial Neural Networks
## Explanation
blah
## Use Cases
blah blah
## Common Issues
### Loop War
A loop war occurs when a logical loop is formed in the layout of your ANN. To combat this, add some logic to the `fire()` method such as a boolean `hasFired` flag or a counter of some kind.
### OOP Pointers
One important thing to note about the implementation code in the **NodeClass* chapter utilizes important OOP concepts. In the following code, the last two lines perform the function on the same object. By default, objects are passed using pointers instead of deep-copying the object to a new location in memory. For better control over this process, use a non-managed runtime language such as C++;

```
// Create objects
SomeObject someObject = new SomeObject();
ArrayList<SomeObject> arrayList = new ArrayList();

// COPY pointer of object to array.
arrayList.addElement(someObject);

// Both of these commands do the same thing
// to the same object in memory.
someObject.doStuff();
arrayList[0].doStuff();
```