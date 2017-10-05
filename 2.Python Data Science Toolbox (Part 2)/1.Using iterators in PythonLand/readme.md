# 1. Introduction to Iteretors
## 1.1 Iterable:
*lists, strings, dictionaries, file connections are iterable*  +  enumrrate() and zip()

**INFO:** for loop are used on those iterables

**INFO 2 :**  you can do pd.read_csv(filename, chunksize=100). **This creates an iterable reader object, which means that you can use next() on it.**

iterable  -> iter() -> iterator -> next()

![Iterabls vs Iterators Image](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/1.%20Iterators%20vs%20iterables.PNG)

iterable  -> iter() -> iterator -> next() process

![Iterabls vs Iterators process image](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/2.Iterators%20vs%20iterables%20process.PNG)

### 1.1.1 Breaking down the for loop
```python
  for i in rage(0, 11):
      print(i)
 ```
 
   **rage(0, 11)** : Iterable
   **i**: Iterator variabls (represent members of iterable)

# 2. Playing with Iterators (enumerate() and zip())

## 2.1 Enumerate()
[enumerate() and zip() video](https://campus.datacamp.com/courses/python-data-science-toolbox-part-2/using-iterators-in-pythonland?ex=6)

*Enumerate()* is a function that takes any **iterable** as an argument such as a list and returns a special **enumerate object** which consists of pairs containing the elements of original iterable along with the index within the iterable.

We can use the function *list()* to turn this **enumerate object** to a **list of tuples**. 

![Enumerate image](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/3.enumrate.PNG)

**Enumarate object** itself is also a **iterable** and we can loop over it.

![Enumerate image](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/4.Enumrate%20unpack.PNG)


## 2.2 Zip()
*zip()* accepts an **arbitrary number of iterables** and returns an **zip object** which is actually **iterator of tuples**
we can turn this **iterator of tuples** into a list using *list()*

![Enumerate image](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/5.%20zip.PNG)

we could use a for loop to iterate over the **zip object** and print the **tuples**

![unpack zip](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/6.unpack%20zip1.PNG)

we could also use the (*) operator to print all the elements

![unpack zip using](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/7.unpack%20zip2.PNG)



# 3. Using iterators to load large files into memory

![file chank size](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/8.chank.PNG)

The object created by pd.readcsv('data.csv', chunksize = 1000) is an **iterable**. So we can iterate over it using a for loop in which each **chunk** will be a DataFrame

![Example of chank size](https://github.com/upalr/Python-camp/blob/master/2.Python%20Data%20Science%20Toolbox%20(Part%202)/1.Using%20iterators%20in%20PythonLand/images/9.chank.PNG)

**INFO 2 Again :**  you can do pd.read_csv(filename, chunksize=100). **This creates an iterable reader object, which means that you can use next() on it.** [DataCamp](https://campus.datacamp.com/courses/python-data-science-toolbox-part-2/bringing-it-all-together-3?ex=11)


``` python
# Import the pandas package
import pandas as pd

# Initialize reader object: df_reader
df_reader = pd.read_csv('ind_pop.csv', chunksize=10)

# Print two chunks
print(next(df_reader))                  # print first chunk (row 0 to 9)
print(next(df_reader))                  # print second chunk (row 10 to 19)
```
Output: 

