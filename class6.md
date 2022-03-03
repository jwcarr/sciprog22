# Scientific Programming: A Crash Course

## Class 6 – Online Experiments – 3 Mar 2022

Today we're going to expand our horizons beyond Python! But we won't leave Python behind completely – you can still use it to analyze the data you collect. To keep things familiar, we will continue with the same numerosity estimation experiment that we played with in the last class. This means you can still use any Python analysis code that you wrote before – the only thing that's changing is that the experiment will now be run in the browser.


## JavaScript 

The only programming language that web browsers understand is [JavaScript](https://www.javascript.com). This is because there would be security issues if websites could just run any random program on your computer. The JavaScript language is strictly limited in what it can do. For example, JavaScript cannot read or write files to your computer. However, like Python, JavaScript is a high-level programming language with a syntax that is quite English-like. Many of the core constructs will seem familiar, even if the precise syntax is a little different. Here are a few examples:

**Variable creation in Python:**

```python
magic_number = 3.14159
```

**Variable creation in JavaScript:**

```javascript
var magic_number = 3.14159;
```

**If-statement in Python:**

```python
if magic_number < 4:
	print('Magic number is less than 4')
```

**If-statement in JavaScript:**

```javascript
if (magic_number < 4) {
	console.log('Magic number is less than 4');
}
```

**For-loop in Python:**

```python
for thing in list_of_things:
	print(thing)
```

**For-loop in JavaScript:**

```javascript
for (thing of list_of_things) {
	console.log(thing);
}
```

**Function in Python:**

```python
def my_func(argument1, argument2):
	return argument1 + argument2
```

**Function in JavaScript:**

```javascript
function my_func(argument1, argument2) {
	return argument1 + argument2;
}
```

One of the nice things about working with JavaScript is that you don't need very much software to get started. All you need is a web browser (to run the experiment) and a code editor app (to edit the code). As I mentioned in the last class, there are many different code editors available that work with multiple languages, including both Python and JavaScript:

- [Atom](https://atom.io)

- [Brackets](https://brackets.io)

- [Sublime Text](https://www.sublimetext.com)

- [VSCode](https://code.visualstudio.com)

If you don't already have a favorite text editor, I would recommend that you download one now (just pick whichever one looks prettiest to you – they are mostly equivalent in functionality). The general usage pattern is that you use the text editor to write and edit the code, and you use the web browser to run the code.

## jsPsych

jsPsych is a JavaScript library for online experiments and is roughly equivalent to PsychoPy. It provides a lot the core infrastructure you need for experiments, like creating stimuli, randomizing trials, and capturing participant responses. You can read more about it here: https://www.jspsych.org jsPsych is not the only library for building online experiments, but it is increasingly becoming the standard package that people use for this purpose.

Note that you don't actually need to download jsPsych. Instead, the jsPsych library is linked in your script file and downloaded automatically by each participant when they open the experiment.

If you would like to explore jsPsych further, a good place to start is the tutorial on the jsPsych website: https://www.jspsych.org/7.1/tutorials/rt-task/ I'd also highly recommend this course from my former PhD advisor, Kenny Smith: https://kennysmithed.github.io/oels2021/ It's a little bit more focused on language experiments, but there's still lots of general advice that will apply whatever type of experiment you want to run.


## Activities

Make sure you've downloaded the three Python files for this class (`class6/experiment.html`, `class6/results.py`, and `class6/transform.py`) and then work through the following activities, which are roughly in order of difficulty. Feel free to continue working on your PsychoPy code as well.

### Experiment activities

1. Open `experiment.html` in a web browser to check that everything works correctly.

2. Once you get the data at the end, copy it into a new file, save it as `.json`, and convert the raw data to CSV for analysis (using `transform.py`).

3. Use `results.py` to look at your results. Increase `N_REPS` and try the experiment several times to collect a larger dataset.

4. Change the background color to black and the foreground color (text and dots) to white. You might need to look around online to find out how to change colors (hint: you will probably want to add a new `<style>` tag in the HTML where you can specify formatting parameters).

5. I didn't add any comments to the code to explain how it works. Read through the code and add you own comments to explain how different parts of the code work.

6. The code has the same issue as the PsychoPy version: dots can potentially overlap. Write a function to generate *n* dot positions that are non-overlapping (i.e. by taking into account the `DOT_RADIUS`). You might find it easier to write a Python version first and then try to translate it to JavaScript.

7. Make an option that controls how densely clustered the dots are? Is the task easier if the dots are more densely clustered? Again, you might find it easier to write a Python version first. This is quite hard – first you need to decide what it even means for dots to be densely or sparsely clustered.

### Analysis activities

1. If you didn't already, create a new notebook to record your analyses.

2. Collect data from both the PsychoPy version of the experiment and the jsPsych version, and then compare the results. Are there any differences? For example, maybe reaction times are recorded differently in each version.

3. If you didn't already do this in the last class, try plotting the correct number of dots (*x*-axis) against the number of dots estimated by participants (*y*-axis). Are you able to replicate the effect where people underestimate larger numbers?

4. Instead of having a separate CSV file for each participant, it might make more sense to merge everything together into a single CSV file with an extra `subject_id` column. Can you figure out a way to do this? Perhaps it would be best to write a preprocessing script that merges all the data together into one big file.

5. Try to make a plot that captures across-participant variation by using a box plot or violin plot. If you feel more confident in R, try using R to read in the data and make the plots.


## Homework

Spend more time with both PsychoPy and jsPsych. Try to implement the same experiment in both Python and JavaScript to get a feel for the advantages and disadvantages of each language. If you don't have any experiment ideas, try creating an experiment where participants have to memorize a list of words and then recall them in a test phase.
