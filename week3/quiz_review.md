The equals() method is equivalent to the == operator, unless overridden

- If we create a custom class and don't override the .equals method, it does work exactly the same as == 
- With strings, the .equals is already overridden so it does check for value

String a = new "hello";
String b = new "hello";

a == b // false, different memory locations
a.equals(b), because the string class overrides equals, it checks for value, instead of reference



How to declare main method






Given the following definition of class, which member variables are accessible from OUTSIDE the package com.enthu.qb?
 

 package com.enthu.qb;

public class TestClass{

   int i; // not available outside of package

   public int j; // anywhere

   protected int k; // only for sub-classes or in the package

   private int l;

}






Which of the following uses of variable arguments is syntactically correct?
Which of the following uses of variable arguments is syntactically correct? Choose all that apply.

public void someMethod(int...a, int b){...}

public void someMethod(int...a, int...b){...}

public void someMethod(int a, int...b){...}

public void someMethod(int...a){...}