# 1 Welcome to the course!
## 1.1 Reading a Text file
![1.reading-text-file.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/1.reading-text-file.PNG)

For large files, we may not want to print all of their content to the shell: you may wish to print only the first few lines. Enter the readline() method, which allows you to do this. When a file called file is open, you can print out the first line by executing file.readline(). If you execute the same command again, the second line will print, and so on.

## 1.2 Writing to a File
![2.writing-text-file.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/2.writing-text-file.PNG)

## 1.3 Context Manager With 
you can avoid having to close the connection to the file by using a **with statement**. This allows you to create a context in which you can execute commands with the file open. Once out of this clause or context the file is no longer open and for this reason **with** is called a **context manager**. **Best practice is using the with statement as you don't need to close the file again.** 

![3.text-file-with-context-manager.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/3.text-file-with-context-manager.PNG)

# 2 The importance of flat files in data science
## 2.1 Flat Files
![4.flat-files.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/4.flat-files.PNG)

## 2.2 File Extenson
![5.file-extension.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/5.file-extension.PNG)

![6.tab-delimited-file.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/6.tab-delimited-file.PNG)

## 2.3 How do you import flast files?
If they consist entirely of numbers and we want to store them as **Numpy array** we could use the package **Numpy**. If instead we want to store data in a **DataFrame** we would use **Pandas**. Most of the time you will use one of these options.

![7.import-flat-files.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/7.import-flat-files.PNG)


# 3 Importing flat files using NumPy
## 3.1 Why Numpy?
![8.why-numpy.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/8.why-numpy.PNG)

## 3.2 Importing flat files using NumPy
![9.importing-flat-files-using-numpy.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/9.importing-flat-files-using-numpy.PNG)


## 3.3 Customize your numpy import 
![10.customization.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/10.customization.PNG)

![11.customization.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/11.customization.PNG)

![12.customization.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/12.customization.PNG)

## 3.4 mixed types 
**loadtext()** is grate for basic cases but it barkes down when we have mixed datatypes

![13.mixed-data-types.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/13.mixed-data-types.PNG)


## Example 1: Customizing your NumPy import
What if there are rows, such as a header, that you don't want to import? What if your file has a delimiter other than a comma? What if you only wish to import particular columns?

There are a number of arguments that np.loadtxt() takes that you'll find useful: delimiter changes the delimiter that loadtxt() is expecting, for example, you can use ',' and '\t' for comma-delimited and tab-delimited respectively; skiprows allows you to specify how many rows (not indices) you wish to skip; usecols takes a list of the indices of the columns you wish to keep.

The file that you'll be importing, digits_header.txt,

*has a header
*is tab-delimited.

```python
# Import numpy
import numpy as np

# Assign the filename: file
file = 'digits_header.txt'

# Load the data: data
data = np.loadtxt(file, delimiter='\t', skiprows=1, usecols=[0, 2])

# Print data
print(data)
```


## Example 2: Importing different datatypes

The file seaslug.txt

* has a text header, consisting of strings
* is tab-delimited.

These data consists of percentage of sea slug larvae that had metamorphosed in a given time period. Read more here.

**Due to the header,**
1. if you tried to import it as-is using np.loadtxt(), Python would throw you a *ValueError* and tell you that it *could not convert string to float.* There are two ways to deal with this: firstly, you can set the data type argument *dtype* equal to *str* (for string).

2. Alternatively, you can skip the first row as we have seen before, using the skiprows argument.

```python
# Assign filename: file
file = 'seaslug.txt'

# Import file: data
data = np.loadtxt(file, delimiter='\t', dtype=str)

# Print the first element of data
print(data[0])

# Import data as floats and skip the first row: data_float
data_float = np.loadtxt(file, delimiter='\t', dtype=float, skiprows=1)

# Print the 10th element of data_float
print(data_float[9])

# Plot a scatterplot of the data
plt.scatter(data_float[:, 0], data_float[:, 1])
plt.xlabel('time (min.)')
plt.ylabel('percentage of larvae')
plt.show()

```

## Example 3: Working with mixed datatypes (1)    Using[np.genfromtx()]

Much of the time you will need to import datasets which have different datatypes in different columns; one column may contain strings and another floats, for example. The function np.loadtxt() will freak at this. There is another function, **np.genfromtxt()**, which can handle such structures. If we pass dtype=None to it, it will figure out what types each column should be.

Import 'titanic.csv' using the function np.genfromtxt() as follows:

> data = np.genfromtxt('titanic.csv', delimiter=',', names=True, dtype=None)

Here, the first argument is the filename, the second specifies the delimiter , and the third argument names tells us there is a header. Because the data are of different types, data is an object called a structured array. Because numpy arrays have to contain elements that are all the same type, the structured array solves this by being a 1D array, where each element of the array is a row of the flat file imported. You can test this by checking out the array's shape in the shell by executing np.shape(data).

*Acccessing rows and columns of structured arrays is super-intuitive: to get the ith row, merely execute data[i] and to get the column with name 'Fare', execute data['Fare'].*

**Print the entire column with name Survived to the shell. What are the last 4 values of this column?**
```python
data['Survived'][-5:-1]
array([0, 1, 0, 1])
```

## Example 4: Working with mixed datatypes (2)   Using[np.recfromcsv()]

You have just used np.genfromtxt() to import data containing mixed datatypes. There is also another function np.recfromcsv() that behaves similarly to np.genfromtxt(), except that its default dtype is None. In this exercise, you'll practice using this to achieve the same result
<br />
<br />
<br />


# 3 Importing flast files using pandas
## 3.1 What a Data Scientis needs
![14.what-a-data-scientist-needs.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/14.what-a-data-scientist-needs.PNG)

## 3.2 Manipulating Pandas DataFrames
![15.manipulating-pandas-dataframes.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/15.manipulating-pandas-dataframes.PNG)

## 3.3 Importing Using Pandas
![16.importing-using-pandas.PNG](https://github.com/upalr/Python-camp/blob/master/3.%20Importing%20Data%20in%20Python%20(Part%201)/1.%20Introduction%20and%20flat%20files/images/16.importing-using-pandas.PNG)




## Example 1: Using pandas to import flat files as DataFrames (1)
In the last exercise, you were able to import flat files containing columns with different datatypes as numpy arrays. However, the DataFrame object in pandas is a more appropriate structure in which to store such data and, thankfully, we can easily import files of **mixed data types as DataFrames** using the pandas functions read_csv() and read_table().


## Example 2: Using pandas to import flat files as DataFrames (2)

In the last exercise, you were able to import flat files into a pandas DataFrame. **As a bonus, it is then straightforward to retrieve the corresponding numpy array using the attribute values**
```pyton
# Assign the filename: file
file = 'digits.csv'

# Read the first 5 rows of the file into a DataFrame: data
data = pd.read_csv(file, nrows=5, header=None) # header (there is no header in this file)

# Build a numpy array from the DataFrame: data_array
data_array = data.values

# Print the datatype of data_array to the shell
print(type(data_array))
```

# Customizing your pandas import

**The pandas package is also great at dealing with many of the issues you will encounter when importing data as a data scientist,** <br />
such as: 
1. comments occurring in flat files,
2. empty lines and missing values. 
3. Note that missing values are also commonly referred to as NA or NaN. 

[Exercise Link](https://campus.datacamp.com/courses/importing-data-in-python-part-1/introduction-and-flat-files-1?ex=18)
<br />

```pyton
# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Assign filename: file
file = 'titanic_corrupt.txt'

# Import file: data
data = pd.read_csv(file, sep='\t', comment='#', na_values='Nothing')

# Print the head of the DataFrame
print(data.head())

# Plot 'Age' variable in a histogram
pd.DataFrame.hist(data[['Age']])
plt.xlabel('Age (years)')
plt.ylabel('count')
plt.show()
```

