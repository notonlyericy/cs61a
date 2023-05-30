### Course
[CS61A](https://inst.eecs.berkeley.edu/~cs61a/su20/)

---
### Notes
#### Pure Functions
Pure functions have the property that applying them has _no effects_ beyond returning a value. Moreover, a pure function must always return the _same value_ when called twice with the same arguments
```python
abs(-2) # pure
print(1) # non-pure  display 1 and return none
```

---
#### Higher Order Functions
A **higher order function**(HOF) is a function that manipulates other functions by taking in functions as arguments, returning a function, or both.

A powerful **abstraction** tools that allow us to express certain general patterns as named concepts in our programs.

```python
def compose1(f, g): # function(s) as auguments
    def h(x):
        return f(g(x))
    return h # return a function
```
##### Curring
Convert a function that takes multiple arguments into a chain of functions that each take a single argument.
```python
def curried_pow(x):
    def h(y):
        return pow(x, y)
    return h

curried_pow(2)(3)
```
pow(x, y) => curried\_pow(2)(3)
