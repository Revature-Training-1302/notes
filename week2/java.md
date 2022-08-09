## IntelliJ Tips:
1. Right-click on the class.
2. Select Generate.
3. Choose what you want to generate(constructor, getter, setter, etc.)
4. Select the fields you want it to apply to (hold shift to select more than one)
5. As always, make sure you know how to do it without the shortcut before you use the shortcut

## Non-Access Modifiers
- static - if we use this keyword, it attaches the variable/method to the class rather than an instance
    - static methods can be called from the class or the object
    - non-static method can only be called from an object
    - It's good to use static methods when you don't care about state (member variables)
    - We don't want to use static methods if we need access to member variables (then we can't reference "this")
    - static variables are attached to the class
    - We only want to use static variables if they are the same for the entire class (ex: the value of PI)
    - We do NOT want static variables if we want to keep track of state
    - If we want make it static, we add the keyword "static" before it
- final - we can't change it
    - variables - we can't reassign the value
    - methods
    - classes


## Scope
- Method Scope
- Class Scope
- Block Scope
- In general, different scopes are denoted by {}
- If we define something within a scope (or in a set of {}), then we can't use it outside that scope