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