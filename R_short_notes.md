# What is R
R is a popular programming language used for statistical computing and graphical presentation.

Its most common use is to analyze and visualize data.

## How to Install R 
To install R, go to https://cloud.r-project.org/ and download the latest version of R for Windows, Mac or Linux.

Then install Rstudio https://posit.co/download/rstudio-desktop/

## Syntax
To output text in R, use single or double quotes:
```R 
"Hello World!"
```
To output numbers, just type the number (without quotes):
``` R
 5
10
25
```
To do simple calculations, add numbers together:
```R
5 + 5
```
## Print
Unlike many other programming languages, you can output code in R without using a print function:
```R
 "Hello World!"
  ```

However, R does have a print() function available if you want to use it. This might be useful if you are familiar with other programming languages, such as Python, which often uses the print() function to output code.
```R
print("Hello World!")
```
And there are times you must use the print() function to output code, for example when working with for loops (which you will learn more about in a later chapter):
```R
for (x in 1:10) {
  print(x)
}
```
## Comments 
Comments can be used to explain R code, and to make it more readable. It can also be used to prevent execution when testing alternative code.

Comments starts with a #. When executing code, R will ignore anything that starts with #.

This example uses a comment before a line of code:
```R
# This is a comment
"Hello World!"
```
we can use comments at the same line
```R
"Hello World!" # This is a comment
```
## Multiline Comments
```R
# This is a comment
# written in
# more than just one line
"Hello World!"
```
## Creating Variables in R
Variables are containers for storing data values.

R does not have a command for declaring a variable. A variable is created the moment you first assign a value to it. To assign a value to a variable, use the `<-` sign. To output (or print) the variable value, we can also use `=` sign for declaring a variable .
``` R
name <- "John"
age <- 40
name = "John"
age = 40
```
But generally in R we use this `<-` sign for declaring a variable .
## Print / Output Variables
Compared to many other programming languages, you do not have to use a function to print/output variables in R. You can just type the name of the variable:
```R
name <- "John Doe"

name # auto-print the value of the name variable
```
## Cncatination 
You can also concatenate, or join, two or more elements, by using the `paste()` function.

To combine both text and a variable, R uses comma `(,)`:
```R
text <- "awesome"

paste("R is", text)
```
`Note `: if you try to combine a string (text) and a number, R will give you an error:
## Multiple Variables
R allows you to assign the same value to multiple variables in one line:

```R
# Assign the same value to multiple variables in one line
var1 <- var2 <- var3 <- "Orange"

# Print variable values
var1
var2
var3
 ```
## Variable Names
A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume).

Rules for R variables are:
1. A variable name must start with a letter and can be a combination of letters, digits, period(.)
and underscore(_). If it starts with period(.), it cannot be followed by a digit.
2. A variable name cannot start with a number or underscore (_)
3. Variable names are case-sensitive (age, Age and AGE are three different variables)
4. Reserved words cannot be used as variables (TRUE, FALSE, NULL, if...)
```R
# Legal variable names:
myvar <- "John"
my_var <- "John"
myVar <- "John"
MYVAR <- "John"
myvar2 <- "John"
.myvar <- "John"

# Illegal variable names:
2myvar <- "John"
my-var <- "John"
my var <- "John"
_my_var <- "John"
my_v@ar <- "John"
TRUE <- "John"
```
## Data types
Variables can store data of different types, and different types can do different things.

In R, variables do not need to be declared with any particular type, and can even change type after they have been set:
```R
my_var <- 30 # my_var is type of numeric
my_var <- "Sally" # my_var is now of type character (aka string)
```
| Data Type  |   Example   |  `typeof()` |
| ----------| --------| ----------|
|Numeric (double) | x <- 3.14 | "double"|
| Integer | y <- 7L | "integer"|
| Complex | z <- 2+3i | "complex" |
| Logical | f <- false | "false" |
| Character | s <- "hello" | "character"|
| Raw | r <- charToRaw("A") | "raw" |   

### But why is there are two different kinds of `Data Types` for Numbers ?
`Numeric` Data Type contains both any Number with decimals and without decimals . `Integer` are also `Numeric` Data Types without decimals , ` integer` Data Type is used when you are certain that you will never create a variable that should cantains a decimal .

To create an `integer` variable, you must use the letter `L` after the integer value:
```R
x <- 1000L
y <- 55L

# Print values of x and y
x
y

# Print the class name of x and y
class(x)
class(y)
```
## Type Conversion 
You can convert from one type to another with the following functions:

1. `as.numeric()`
2. `as.integer()`
3. `as.complex()`
``` R
x <- 1L # integer
y <- 2 # numeric

# convert from integer to numeric:
a <- as.numeric(x)

# convert from numeric to integer:
b <- as.integer(y)
```
In general we don't prefer to to convert a complex number in to `numeric` or `integer`. 

## Built-in Math Functions
R also has many built-in math functions that allows you to perform mathematical tasks on numbers.

| Function                                       | Example in R         | Output                         |
| ---------------------------------------------- | -------------------- | ------------------------------ |
| `abs(x)` – absolute value                      | `abs(-7)`            | `7`                            |
| `sqrt(x)` – square root                        | `sqrt(16)`           | `4`                            |
| `ceiling(x)` – smallest integer ≥ x            | `ceiling(3.2)`       | `4`                            |
| `floor(x)` – largest integer ≤ x               | `floor(3.8)`         | `3`                            |
| `trunc(x)` – truncate decimal part             | `trunc(3.9)`         | `3`                            |
| `round(x, n)` – round to n decimals            | `round(3.14159, 2)`  | `3.14`                         |
| `signif(x, n)` – round to n significant digits | `signif(123.456, 4)` | `123.5`                        |
| `exp(x)` – e^x                                 | `exp(1)`             | `2.718282`                     |
| `log(x)` – natural log (base e)                | `log(2.718282)`      | `1`                            |
| `log10(x)` – base 10 log                       | `log10(1000)`        | `3`                            |
| `log2(x)` – base 2 log                         | `log2(8)`            | `3`                            |
| `cos(x)` – cosine (radians)                    | `cos(pi/3)`          | `0.5`                          |
| `sin(x)` – sine (radians)                      | `sin(pi/2)`          | `1`                            |
| `tan(x)` – tangent (radians)                   | `tan(pi/4)`          | `1`                            |
| `acos(x)` – inverse cosine                     | `acos(0.5)`          | `1.047198` (= π/3)             |
| `asin(x)` – inverse sine                       | `asin(1)`            | `1.570796` (= π/2)             |
| `atan(x)` – inverse tangent                    | `atan(1)`            | `0.785398` (= π/4)             |
| `max(x1,x2,...)` – maximum value               | `max(3, 7, 2)`       | `7`                            |
| `min(x1,x2,...)` – minimum value               | `min(3, 7, 2)`       | `2`                            |
| `sum(x)` – sum of elements                     | `sum(c(1,2,3,4))`    | `10`                           |
| `prod(x)` – product of elements                | `prod(c(1,2,3,4))`   | `24`                           |
| `mean(x)` – average                            | `mean(c(2,4,6,8))`   | `5`                            |
| `median(x)` – median                           | `median(c(1,3,5,7))` | `4`                            |
| `var(x)` – variance                            | `var(c(1,2,3))`      | `1`                            |
| `sd(x)` – standard deviation                   | `sd(c(1,2,3))`       | `1`                            |
| `factorial(x)` – factorial                     | `factorial(5)`       | `120`                          |
| `choose(n, k)` – n choose k (combinations)     | `choose(5,2)`        | `10`                           |
| `gamma(x)` – gamma function                    | `gamma(6)`           | `120` (= (6−1)!)               |
| `digamma(x)` – derivative of log gamma         | `digamma(1)`         | `-0.577216` (Euler’s constant) |

## Strings 
You can assign a multiline string to a variable like this:

```R
str <- "Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."

str # print the value of str
```
### String Functions
If you want the line breaks to be inserted at the same position as in the code, use the `cat()` function:

```R
str <- "Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."

cat(str)
```
```R
str <- "Hello" 
```

|Function | Example | Uses |
|---------| --------| -----|
|`nchar()` | nchar(str) | to find number of characters in a string 
|` grepl()` |grepl("H", str) | checks if a character or a sequence of characters are present in a string:
|`paste()` |paste(str1, str2) |to merge/concatenate two strings:|
## R Escape Characters

## Operators
1. Arithmetic operators
2. Assignment operators
3. Comparison operators
4. Logical operators
5. Miscellaneous operators

### Arithmetic Operators
| Operator|	Name| Example	|
| ------- |------- | -------|
| +	      | Addition       |	x + y	  |
| -	      | Subtraction    |	x - y	|
| *	      | Multiplication |	x * y	|
| /	      | Division	      |  x / y	|
| ^	      | Exponen        |  t	x ^ y	|
| %%      |	Modulus (Remainder from division) |	x %% y	|
| %/%     |	Integer Division	|x%/%y |

### Assignment Operators
```R
my_var <- 3

my_var <<- 3

3 -> my_var

3 ->> my_var

my_var # print my_var
```
**Note:** <<- is a global assigner. You will learn more about this in the Global Variable chapter.

It is also possible to turn the direction of the assignment operator.

x <- 3 is equal to 3 -> x
### The Global Assignment Operator
Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the global assignment operator `<<-`
```R
my_function <- function() {
txt <<- "fantastic"
  paste("R is", txt)
}

my_function()

print(txt)
```

## Comparison Operators

| Operator | Meaning                  | Example  | Output  |
| -------- | ------------------------ | -------- | ------- |
| `>`      | Greater than             | `7 > 3`  | `TRUE`  |
| `<`      | Less than                | `7 < 3`  | `FALSE` |
| `==`     | Equal to                 | `7 == 7` | `TRUE`  |
| `!=`     | Not equal to             | `7 != 3` | `TRUE`  |
| `>=`     | Greater than or equal to | `7 >= 7` | `TRUE`  |
| `<=`     | Less than or equal to    | `7 <= 3` | `FALSE` |


## Logical Operators

| Operator | Description |
| -------- | ---- |
|& |	Element-wise Logical AND operator. Returns TRUE if both elements are TRUE |
|&&	| Logical AND operator - Returns TRUE if both statements are TRUE |
| ` ` |	Elementwise- Logical OR operator. Returns TRUE if one of the statements is TRUE |
|` `	| Logical OR operator. Returns TRUE if one of the statements is TRUE |
|! |	Logical NOT - Returns FALSE if statement is TRUE |

## Miscellaneous Operators
 
Special Operators in R 

| Operator | Name | Example |
| -------- | ---- | ------- |
| : | Creates a series of numbers in a sequence	 |x <- 1:10 |
| %in%	 | Find out if an element belongs to a vector	| x %in% y| 
|%*%  | Matrix Multiplication	| x <- Matrix1 %*% Matrix2 |

## If Else
```R
a <- 200
b <- 33

if (b > a) {
  print("b is greater than a")
} else if (a == b) {
  print("a and b are equal")
} else {
  print("a is greater than b")
}
```
## While Loop
Break
```R
i <- 1
while (i < 6) {
  print(i)
  i <- i + 1
  if (i == 4) {
    break
  }
}
```
next
```R
i <- 0
while (i < 6) {
  i <- i + 1
  if (i == 3) {
    next
  }
  print(i)
}
```
## for Loop 
```R
# Loop over a sequence 
for (x in 1:10) {
  print(x)
}

#loop over a Vector 
fruits <- c("apple", "banana", "mango")
for (f in fruits) {
  print(paste("I like", f))
}

# Looping over a List 
fruits <- list("apple", "banana", "cherry")
for (x in fruits) {
  print(x)
}
```
## Functions 
```R
my_function <- function(country = "Norway") {
  paste("I am from", country)
}

my_function("Sweden")
my_function("India")
my_function() # will get the default value, which is Norway
my_function("USA")
```
## Recursion 
```R
tri_recursion <- function(k) {
  if (k > 0) {
    result <- k + tri_recursion(k - 1)
    print(result)
  } else {
    result = 0
    return(result)
  }
}
tri_recursion(6)
```
## Data Structures
1. Vectors
1. Lists
1. Matrices
1. Arrays
1. Data Frames
1. Factors 

| Data Structure | Contains |Same Type? | Use Case|
| -------------- | -------- | --------- | ------- |
|Vector |	Single row of values	|Yes	|Simple sequences|
|List |	Multiple types |	No|	Grouped mixed data |
|Matrix |	2D same-type values	| Yes |	Tables with numeric data |
|Array|	Multi-dimensional values |	Yes	|3D or higher-dimensional data |
|Data Frame |	Columns of mixed types|	No	|Working with tabular data |

## Vectors
A vector is simply a list of items that are of the same type.

To combine the list of items to a vector, use the c() function and separate the items by a comma.

```R
# Vector of strings
fruits <- c("banana", "apple", "orange")

# Vector of numerical values
numbers <- c(1, 2, 3)
```
To create a vector with numerical values in a sequence, use the `:` operator:
```R
# Vector with numerical values in a sequence
numbers <- 1:10
```
You can also create numerical values with decimals in a sequence, but note that if the last element does not belong to the sequence, it is not used:
```R
# Vector with numerical decimals in a sequence
numbers1 <- 1.5:6.5
numbers1  # Output [1] 1.5 2.5 3.5 4.5 5.5 6.5

# Vector with numerical decimals in a sequence where the last element is not used
numbers2 <- 1.5:6.3
numbers2  # Output [1] 1.5 2.5 3.5 4.5 5.5
```
### Vector Length
To find out how many items a vector has, use the `length()` function:
```R
fruits <- c("banana", "apple", "orange")

length(fruits)
```
### Sort a Vector
To sort items in a vector alphabetically or numerically, use the `sort()` function:

```R
fruits <- c("banana", "apple", "orange", "mango", "lemon")
numbers <- c(13, 3, 5, 7, 20, 2)

sort(fruits)  # Sort a string
sort(numbers) # Sort numbers
```

### Access Vectors
You can access the vector items by referring to its index number inside brackets `[]`. The first item has index 1, the second item has index 2, and so on:

```R
fruits <- c("banana", "apple", "orange")

# Access the first item (banana)
fruits[1]
```
You can also access multiple elements by referring to different index positions with the` c()` function:

```R
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access the first and third item (banana and orange)
fruits[c(1, 3)]
```
You can also use negative index numbers to access all items except the ones specified:

```R
fruits <- c("banana", "apple", "orange", "mango", "lemon")

# Access all items except for the first item
fruits[c(-1)]
```

### Repeat Vectors

To repeat vectors, use the `rep()` function:

Repeat each value:
```R
repeat_each <- rep(c(1,2,3), each = 3)

repeat_each # Output [1] 1 1 1 2 2 2 3 3 3
```

Repeat the sequence of the vector:
```R
repeat_times <- rep(c(1,2,3), times = 3)

repeat_times # output [1] 1 2 3 1 2 3 1 2 3
```

Repeat each value independently:
```R
repeat_indepent <- rep(c(1,2,3), times = c(5,2,1))

repeat_indepent # Output [1] 1 1 1 1 1 2 2 3
```

To make bigger or smaller steps in a sequence, use the `seq() `function:
```R
numbers <- seq(from = 0, to = 100, by = 20)

numbers # Output [1]   0  20  40  60  80 100
```

## Lists

A list in R can contain many different data types inside it. A list is a collection of data which is ordered and changeable.

To create a list, use the` list()` function:
```R
# List of strings
thislist <- list("apple", "banana", "cherry")

# Print the list
thislist
```
### Access Lists
You can access the list items by referring to its index number, inside brackets. The first item has index 1, the second item has index 2, and so on:

```R
thislist <- list("apple", "banana", "cherry")

thislist[1]
```
`Note` : In R , The first Item starts from Index `1` . Unlike `Python ` or any other language Index doesn't starts from `0`

### List Length
To find out how many items a list has, use the `length() `function:

```R
thislist <- list("apple", "banana", "cherry")

length(thislist)
```
### Check if Item Exists
To find out if a specified item is present in a list, use the `%in%` operator:

```R
thislist <- list("apple", "banana", "cherry")

"apple" %in% thislist
```

### Add List Items
To add an item to the end of the list, use the append() function:

```R
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange")
```

To add an item to the right of a specified index, add "after=index number" in the append() function:

```R
thislist <- list("apple", "banana", "cherry")

append(thislist, "orange", after = 2)
```

You can specify a range of indexes by specifying where to start and where to end the range, by using the : operator:

```R
thislist <- list("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")

(thislist)[2:5]
```
There are several ways to join, or concatenate, two or more lists in R.

The most common way is to use the `c()` function, which combines two elements together:
```R
list1 <- list("a", "b", "c")
list2 <- list(1,2,3)
list3 <- c(list1,list2)

list3
```
## Matrices 

A matrix is a two dimensional data set with columns and rows.

A matrix can be created with the `matrix()` function. Specify the `nrow `and `ncol` parameters to get the amount of rows and columns:

``` R
# Create a matrix
thismatrix <- matrix(c(1,2,3,4,5,6), nrow = 3, ncol = 2)

# Print the matrix
thismatrix
```
### Access Matrix Items
You can access the items by using` [ ]` brackets. The first number "1" in the bracket specifies the row-position, while the second number "2" specifies the column-position:
``` R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)

thismatrix[1, 2]
thismatrix[2,]  # The whole row can be accessed if you specify a comma after the number in the bracket:

thismatrix[,2]   # The whole column can be accessed if you specify a comma before the number in the bracket:
```
### Access More Than One Row
More than one row and column can be accessed if you use the  `c()` function:
``` R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)
thismatrix[c(1,2),]
# output 
#      [,1]     [,2]     [,3]   
# [1,] "apple"  "orange" "pear" 
# [2,] "banana" "grape"  "melon"

thismatrix[, c(1,2)]
# output 
#      [,1]     [,2]       
# [1,] "apple"  "orange"   
# [2,] "banana" "grape"    
# [3,] "cherry" "pineapple"
```
### Add Rows and Columns

Use the` cbind()` function to add additional columns in a Matrix:
``` R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)

newmatrix <- cbind(thismatrix, c("strawberry", "blueberry", "raspberry"))

newmatrix
#      [,1]     [,2]        [,3]    [,4]        
# [1,] "apple"  "orange"    "pear"  "strawberry"
# [2,] "banana" "grape"     "melon" "blueberry" 
# [3,] "cherry" "pineapple" "fig"   "raspberry" 
```
**Note** : Note: The cells in the new column must be of the same length as the existing matrix.

Use the `rbind() `function to add additional rows in a Matrix:  
``` R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange","grape", "pineapple", "pear", "melon", "fig"), nrow = 3, ncol = 3)

newmatrix <- rbind(thismatrix, c("strawberry", "blueberry", "raspberry"))

newmatrix
#      [,1]         [,2]        [,3]       
# [1,] "apple"      "orange"    "pear"     
# [2,] "banana"     "grape"     "melon"    
# [3,] "cherry"     "pineapple" "fig"      
# [4,] "strawberry" "blueberry" "raspberry"
```

**Note** : Note: The cells in the new row must be of the same length as the existing matrix.

### Remove Rows and Columns

Use the` c() `function to remove rows and columns in a Matrix:
``` R
#Remove the first row and the first column
thismatrix <- thismatrix[-c(1), -c(1)]
```

To find out if a specified item is present in a matrix, use the `%in%` operator:
``` R
"apple" %in% thismatrix
```

Use the` dim()` function to find the number of rows and columns in a Matrix:
``` R
dim(thismatrix)
```

Use the `length() `function to find the dimension of a Matrix:
```R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)

length(thismatrix) #Total cells in the matrix is the number of rows multiplied by number of columns.

# In the example above: Dimension = 2*2 = 4.
```
### Loop Through a Matrix
``` R
thismatrix <- matrix(c("apple", "banana", "cherry", "orange"), nrow = 2, ncol = 2)

for (rows in 1:nrow(thismatrix)) {
  for (columns in 1:ncol(thismatrix)) {
    print(thismatrix[rows, columns])
  }
}
```

### Converting two matrices 
Again, you can use the` rbind() `or` cbind() `function to combine two or more matrices together:
``` R
# Combine matrices
Matrix1 <- matrix(c("apple", "banana", "cherry", "grape"), nrow = 2, ncol = 2)
Matrix2 <- matrix(c("orange", "mango", "pineapple", "watermelon"), nrow = 2, ncol = 2)

# Adding it as a rows
Matrix_Combined <- rbind(Matrix1, Matrix2)
Matrix_Combined

# Adding it as a columns
Matrix_Combined <- cbind(Matrix1, Matrix2)
Matrix_Combined
```


