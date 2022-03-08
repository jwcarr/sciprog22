# Scientific Programming: A Crash Course

## Class 7 – Intro to R – 8 Mar 2022

Welcome to the final week of the course! I hope you've enjoyed it so far and have learned at least a few new skills. Today, we're going to dip our toes into *another* language, [R](https://www.r-project.org). Like, Python, R is an open-source programming language; however, it is much more focused on statistics and numerical computation. But don't panic! There is NO statistics in today's class! Instead, I want to introduce you to R from the point of view of *coding* (rather than *doing statistics*). Davide Crepaldi will give you a much more in-depth statistical experience in his [Data Modelling course](https://phdcns.sissa.it/data-modelling-human-cognition-research) in April.


## RStudio

Like Python, there are many different ways to use R. You can use it from the terminal; you can use the standard R app; you can use it from a text editor app like Sublime Text or VSCode, and you can even set up Jupyter Notebooks to work with R. However, the most common way that people use R is through the RStudio IDE (integrated development environment). Essentially, RStudio is an app that provides an interface wrapper around the core R interpreter, and it provides additional features like a script editor, file manager, and a place to view the plots that you generate.

There are some paid versions of RStudio, but we will use the free open-source version, which is available from https://www.rstudio.com/products/rstudio/ (click the "Download RStudio Desktop" button).

Once you've downloaded and installed RStudio, click around some of the menus and buttons to get a general idea of where everything is. The key things to note are the console, where you can type commands, the environment window which shows the variables that have been created, and the file manager which allows you to open files. Try typing some basic commands into the console, like `1 + 1` or `print('hello')`.


## Basic R Syntax

Many of the basic syntactic structures in R are very similar to Python and JavaScript; in fact, I would say that R looks like a kind of hybrid of the two. Try all the R examples below by copying them into the RStudio to make sure you understand everything.

**Variable assignment in Python:**

```python
magic_number = 3.14159
```

**Variable assignment in R:**

```r
magic_number <- 3.14159
3.14159 -> magic_number
assign(magic_number, 3.14159)
```

Note how R offers several different ways to assign a value to a variable; there are some other ways as well, but the standard way is with the `<-` left-pointing arrow.

**If-statement in Python:**

```python
if magic_number < 4:
	print('Magic number is less than 4')
```

**If-statement in R:**

```r
if (magic_number < 4) {
	print('Magic number is less than 4')
}
```

Note that you need to place the condition in parentheses and place the content of the if-statement in curly braces. Because the braces indicate which part of the code is conceptually inside the if-statement, indentation doesn't matter in R (unlike Python). For example, the following pieces of code are also valid, just not as tidy:

```r
if (magic_number < 4) {
print('Magic number is less than 4')
}
```

```r
if (magic_number < 4) { print('Magic number is less than 4') }
```

**For-loop in Python:**

```python
for thing in list_of_things:
	print(thing)
```

**For-loop in R:**

```r
for (thing in list_of_things) {
	print(thing)
}
```

As you can see the for-loop looks almost the same as Python, except again we need to use the parentheses and curly braces. To iterate over a range of numbers, you would do this:

```r
for (num in 1:10) {
	print(num)
}
```

Note that ranges in R are inclusive:inclusive, so `1:10` covers the numbers 1 up-to-and-including 10.

**Function in Python:**

```python
def my_func(argument1, argument2):
	return argument1 + argument2
```

**Function in R:**

```r
my_func <- function(argument1, argument2) {
	return(argument1 + argument2)
}
```

Again we see the use of curly braces where Python uses a colon (`:`) followed by an indented block of code. This difference also applies to other control structures as well; for example, based on what you've learned so far, try writing a while-loop to count up to ten. Can you figure out how to do it?

**Lists in Python:**

```python
my_colors = ['red', 'green', 'blue']
```

**Lists in R:**

```r
my_colors <- list('red', 'green', 'blue')
```

To access an item in the list you use brackets to supply the index to a particular item. For example, to get the first element of the list you would use `my_colors[1]` (note that counting is from 1 in R). Based on what you know so far, use a for-loop to iterate over the `my_colors` lists and print out each color one by one.

It's actually not so common to use lists in R. Because R is strongly focused on statistics and numerical computation, it's much more common to work with vectors, matrices, and data frames.


## Vectors and Matrices

Vectors are basically like NumPy arrays, and they work in more-or-less the same way. To create a vector, you use the `c()` function. I believe C stands for combine because the function combines all its argument together into a vector.

```r
even_numbers <- c(2, 4, 6, 8, 10)
```

Just like NumPy arrays, you can perform operations on a vector which will be applied to all elements. For example, what do you expect to happen if you type this?:

```r
even_numbers * 10
```

Try doing more complex vector operations by combining several operators (`+`, `-`, `*`, `/`, `^`) at the same time.

Of course, you can also perform operations on two vectors:

```r
odd_numbers <- c(1, 3, 5, 7, 9)
even_numbers * odd_numbers
```

but, of course, the two vectors need to be of the same length – check what happens if the two vectors are not of the same length. That reminds me, to find out the length of a vector, just use the `length()` function:

```r
length(odd_numbers)
```

Do you remember the equivalent function in Python?

Matrices are created using the `matrix()` function. You give this function a vector of numbers and specify either the `nrow` or the `ncol` argument; the vector will then be wrapped into a 2D matrix of values with the appropriate number of rows and columns. For example:

```r
numbers <- c(1, 2, 3, 4, 5, 6, 7, 8, 9)
box_of_nine <- matrix(numbers, ncol=3)
print(box_of_nine)
```

Did this do what you expected? Note that the numbers are arranged down the columns rather than along the rows (as you would expect in Python). This goes back to the idea that R is column-major, whereas Python is row-major. You can change this default behavior by using the `byrow` argument:

```r
numbers <- c(1, 2, 3, 4, 5, 6, 7, 8, 9)
box_of_nine <- matrix(numbers, ncol=3, byrow=TRUE)
print(box_of_nine)
```

Note also here that `TRUE` and `FALSE` have to be fully capitalized in R (recall that in Python, they are written only with the first letter capitalized).

Try multiplying a matrix by a vector. Does it work as you expect?


## Scripting and Working with Data

Entering commands directly into the console is not a good long-term way to use R. The reason is that once you close RStudio, everything you typed into the console will be lost. Instead, you should get into the habit of writing scripts, so that the sequence of steps you took is reproducible.

Click the green + button in the top-left corner to create a new script. Type in some code and then run the code. Note that RStudio encourages you to run the code line by line (you select a line and click the green run button). You can also select many lines and run them all. When running a line (or lines) of code, the code is essentially just copied to the console. This can be useful when you're just playing around and exploring different options, but, in my opinion, it also promotes bad habits: Since you can run the lines in any arbitrary order, the actual sequence of steps you took is left undocumented and stored only in your head. It is therefore good practice to make sure your script will run from top to bottom in a fresh console.

Another important concept to understand is the **working directory**. This is the directory (path) where R is currently looking at your computer. If you need to access files, you need to be aware of your working directory so that you can point to the file correctly. you can either pick a directory in the file manager and choose "Set As Working Directory" or you can use the `setwd()` function:

```r
setwd('~/Code/sciprog22/')
```

Once you've set the working directory, it should then be possible to load files. For example, let's load the `example_data.csv` file that we worked with in a previous class:

```r
df  <- read.csv('example_data.csv')
```

This reads the CSV file into a data frame and assigns that data from to the variable name `df`. Print the data frame first to get reacquainted with the dataset, and then try extracting a single column using the `$` syntax:

```r
df$category_system
```

You could also use, for example, the `unique()` function to see the unique values in this column:

```r
unique(df$category_system)
```

Finally, to filter the data frame by one of the columns, you can use a similar syntax to that used in Pandas. For example, here I am extracting all the rows for subject 1 into a new data frame:

```r
df[ df$subject == 1, ]
```

Data frames are very important in R, so it's good to get lots of practice using them. Check out [this tutorial](https://www.tutorialspoint.com/r/r_data_frames.htm), for example, and see if you can apply the examples to the `example_data.csv` data we loaded above.


## Activities

1. Write an R function that tells you what generation you belong to. The function should take a birth year and return the name of the generation. You can look back at the Python code from Class 1 to remind yourself.

2. Write a sum function. The function should take a single variable, `nums` (a vector of numbers) and it should return the sum of those numbers. You may want to look back at the Python code from Class 2 if you feel unsure.

3. Write a product function. The function should take a single variable, `nums` (a vector of numbers) and it should return the product of those numbers.

4. Load the `example_data.csv` that we used in a previous class and try to reproduce some of the things we did back in Class 4 (e.g. calculating accuracy by participant).

5. Load the CSV data you generated with the Count The Dots experiment (either the PsychoPy version or the jsPsych version) and try to make some plots of your data. If you don't have the data, run the experiment again to generate some data. You will need to do some research online to find out how to make plots.


## Homework

Given everything you've learned over the course, think of something you would like to build and try making it a reality. It could just be something simple like the horoscope generator we worked on earlier in the course. You could use Python, JavaScript, or R or a mixture. I'm very keen to hear about the things you've been working on, so do let me know in the final class on Thursday.
