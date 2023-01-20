## Pass-by-Value

When a parameter is pass-by-value, the caller and the callee method operate on two different variables which are copies of each other. Any changes to one variable don't modify the other.

It means that while calling a method, parameters passed to the callee method will be clones of original parameters. Any modification done in callee method will have no effect on the original parameters in caller method.

## Pass-by-Reference

When a parameter is pass-by-reference, the caller and the callee operate on the same object.

It means that when a variable is pass-by-reference, the unique identifier of the object is sent to the method. Any changes to the parameter’s instance members will result in that change being made to the original value.


---
Sources:
- 2022-05-04: [Pass-By-Value as a Parameter Passing Mechanism in Java - Baeldung](https://www.baeldung.com/java-pass-by-value-or-pass-by-reference)

Related:
[java](java.md)

Tags: