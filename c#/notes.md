## 1. Prevents other class override methods/properties
Use the `sealed` keyword on the method or property. The `sealed` modifier must always be used with `override`

Ex:

```C# 
sealed protected override void DoSomething() { //etc... }
```

## 2. Structure type can't inherit

- A `struct` type can't inherit for other class or structure type.
- It can't be the base class of a class.
- However, a structure type **can implement interface**
