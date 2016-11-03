# Codefile Templates

To ensure fast and efficient coding, these templates should be copied in during the preliminary problem grading stage.

### Java
``` Java
import java.util.*;

public class CLASS_NAME {
  public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    String x = scan.nextLine();
    // Problem code goes here.
  }
}
```
***MUST BE SAVED AS *`CLASS_NAME.java`**

### Python
``` Python
#!/bin/python
import sys, io
x = raw_input()
# Program code goes here
```
*** In Python >=3.0, use ***`input()`*** instead of ***`raw_input()`***.***

### C++
``` C++
#include <iostream>
#include <string>
using namespace std;

int main() {
  string x;
  getline(cin, x);
}
```

### C Sharp
``` C#
using System;

public class CLASS_NAME {
  public static void Main() {
    string x = Console.ReadLine();
  }
}
```
***Note that there are some quirks with Mono regarding memory cleanup. Beware if you need to use deep-copy or large list objects.***