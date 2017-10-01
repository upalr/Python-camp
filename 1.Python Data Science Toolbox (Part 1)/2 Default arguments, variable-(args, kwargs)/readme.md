# 1.Scope and user defined function
![alt text](https://github.com/upalr/Python-camp/blob/master/1.Python%20Data%20Science%20Toolbox%20(Part%201)/2%20Default%20arguments%2C%20variable-(args%2C%20kwargs)/1.Scope%20and%20user%20defined%20function.PNG "Logo Title Text 1")


# 2. Scope and nested function
![alt text](https://github.com/upalr/Python-camp/blob/master/1.Python%20Data%20Science%20Toolbox%20(Part%201)/2%20Default%20arguments%2C%20variable-(args%2C%20kwargs)/2.Scope%20and%20nested%20function.PNG "Logo Title Text 1")



# 3. Why we even nesting functions

## 1. Want to use a process number of times in the inner function
you can see the bellow code which can be refactored by using inner function.

```python
def mod2plus5(x1, x2, x3):
   """Retutns the reminder plus 5 of three values."""   
   new_x1 = x1 % 2 + 5
   new_x2 = x2 % 2 + 5
   new_x3 = x3 % 3 + 5
   
   return (new_x1, new_x2, new_x3)
```

Refactored the Code using the inner function bellow:

```python
def mod2plus5(x1, x2, x3):
   """Retutns the reminder plus 5 of three values."""   
   def inner(x):
      """Retutn the reminder plus 5 of a value."""   
      return x % 2 + 5
   
   return (inner(x1), inner(x2), inner(x3))
```
output
```python
print(mod2plus5(1, 2, 3))
output: (6, 5, 6)
```

## 2. returing function (closure)

```python
def raise_val(n):
   """Retutn the inner function."""   
   def inner(x):
      """Raise x to the power of n."""   
      raised = x ** n
      return raised
   return inner 
```
output
```python
square = raise_val(2)
cube =  raise_val(3)
print(square(2), cube(4))
output: 4, 64
```


# 3. Default and Flexiable argument (*args amd **kwargs)

https://campus.datacamp.com/courses/python-data-science-toolbox-part-1/default-arguments-variable-length-arguments-and-scope?ex=9
