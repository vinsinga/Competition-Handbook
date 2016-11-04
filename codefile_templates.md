# Codefile Templates

To ensure fast and efficient coding, these templates should be copied in during the preliminary problem grading stage.

### Java (v8_SE)
``` Java
import java.util.*;

public class CLASS_NAME {
  public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    String x = scan.nextLine();
    System.out.println(x);
    // Problem code goes here.
  }
}
```
***MUST BE SAVED AS *`CLASS_NAME.java`**

### Python (v2.7)
``` Python
#!/bin/python
import sys, io

if __name__ == '__main__':
  x = raw_input()
  print(x)
  # Program code goes here
```
*** In Python >=3.0, use ***`input()`*** instead of ***`raw_input()`***.***

### C++ (v11)
``` C++
#include <iostream>
#include <string>
using namespace std;

int main() {
  string x;
  getline(cin, x);
  cout << x;
  // Program code goes here
}
```

### C Sharp (Mono/.NET Core)
``` C#
using System;

public class CLASS_NAME {
  public static void Main() {
    string x = Console.ReadLine();
    Console.WriteLine(x);
    // Program code goes here
  }
}
```
***Note that there are some quirks with Mono regarding memory cleanup. Beware if you need to use deep-copy or large list objects.***