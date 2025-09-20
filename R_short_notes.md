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
