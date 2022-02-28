# Scientific Programming: A Crash Course

## Class 5 – Building Experiments – 1 Mar 2022

Welcome back! You made it to Week 3! This week we're going to focus on coding experiments, which you will almost certainly need to do at some point during your PhD. Since we are now building experiments, we'll no longer be using Jupyter Notebook; as you can imagine, it doesn't make much sense to run an experiment inside a Notebook. So, this raises a question: What should we use to write Python code?

In theory, you could use the plain text editor that comes bundled with your operating system (Notepad on Windows, TextEdit on Mac); however, these are actually not very good choices for programming, since they are not designed for editing code. They do not, for example, automatically color-code the syntax to make the code more readable; nor do they indent the code automatically or provide keyboard shortcuts for common coding manipulations.

A better option is to use [Spyder](https://www.spyder-ide.org), which you probably already have installed because it's included in the Anaconda distribution. Spyder is what's known as an IDE (an integrated development environment). It includes lots of extra tools that are useful for programming in Python – for example, a file manager, debugger, integrated plot viewer, and so on. Check out the website to get the general idea, or take a look at the app itself.

One limitation of Spyder is that it's Python specific. If you code in lots of different languages, you may prefer to adopt a single, general text editing application that you can use for lots of different things. Indeed, you may already have a preferred editor if you've done a bit of coding before. The advantage of this general approach is that you only have to learn one tool, but the disadvantage is that that tool is less well designed for each specific language. Here are some popular editors that you can investigate:

- [Atom](https://atom.io)

- [Brackets](https://brackets.io)

- [Sublime Text](https://www.sublimetext.com)

- [VSCode](https://code.visualstudio.com)

My personal favorite is Sublime Text, which I use for almost everything I ever do: Bash, CSS, HTML, JavaScript, LaTeX, Markdown, Matlab, PHP, Python, and R. Personally, I find that using a single tool for everything makes me more productive. But even if you don't adopt a text editor today, I would highly recommend that you investigate this in the future and find something that works well for your needs.

Finally, another option is to use the "coder" tool that is provided as part of PsychoPy (see below). This will be sufficient for today, but when we start coding in JavaScript in the next class, you will need a more general purpose text editor that is not specific to Python, so it's worth investigating some of the options above.


## PsychoPy

There are lots of different tools to build experiments, but the most widely used package in the Python ecosystem is PsychoPy. If you're coming from the Matlab world, PsychoPy is roughly equivalent to Psychtoolbox. There are three main ways to use PsychoPy:

1. The PsychoPy "Builder": This allows you to create experiments using a point-and-click visual interface. This can be useful for quickly making something that works, but, in general, it gives you less control and can be more cumbersome to use. You may decide to use the Builder interface in the future, but for the purpose of this course – which is about learning to program – I want you to create your experiments manually without using the Builder.

2. The PsychoPy "Coder": This is essentially just a text editor (like the apps I recommended above), but the Coder is a little more specific to Python and PsychoPy in particular. In the Coder interface, you type the code for your experiment and then hit the green run button to run it.

3. Install PsychoPy as a regular package using `pip` and then run your experiment script from the terminal. Personally, this is what I do because I find the PsychoPy GUI interface to be slow and clunky. However, it can be a bit fiddly to get PsychoPy to install correctly, so it may be easier just to use the PsychoPy Coder (at least for today).

Basically, for today, you should pick either Option 2 or Option 3 and follow the relevant installation instructions below.

### Option 2 – Easy

This option should be relatively painless and straightforward. Go to the PsychoPy website and download the "Standalone PsychoPy": https://www.psychopy.org/download.html The app is quite big and might take some time to download and install. This is because the standalone version of PsychoPy basically bundles everything you need into one giant package – it even incorporates its own internal version of Python.

Once you've installed it, you can open the PsychoPy app and you'll see three windows: The Builder, the Coder and the Runner. Go ahead and close the Builder – you won't need this today. In the Coder interface, you can then open the `experiment.py` code and start playing around with the experiment (see activities below).

### Option 3 – Complicated

If you would like a more minimalist installation, you can install PsychoPy using `pip`:

```python
pip install psychopy
```

although it may be sensible to make a separate virtual environment first if you are comfortable with doing that:

```bash
python3 -m venv psychopy_venv
source psychopy_venv/bin/activate
pip install psychopy
```

Personally, I had a few issues getting this working because there were some other dependencies I needed to install first. So, if you go down this road and bump into issues, it's probably best to opt for Option 2 above. For more info, check PsychoPy page which also explains more options for setting things up with Anaconda: https://www.psychopy.org/download.html

Finally, note that if you choose this option, you won't have access to the Builder or Coder interfaces – just the core PsychoPy package. Therefore you will need to use your own text editor to read/write/run the code.


## Activities

Make sure you've downloaded the two Python files for this class (`class5/experiment.py` and `class5/results.py`) and then work through the following activities, which are roughly in order of difficulty. Get my attention if you need any help.

### Experiment activities

1. Run `experiment.py` to check that everything works correctly.

2. Increase the number of repetitions to four or five and try the experiment again. Use `results.py` to look at your results. Try the experiment several times to see how consistent your results are.

3. Change the background color to black and the foreground color (text and dots) to white. You might need to look around online to find out how to change colors.

4. Make the experiment script more organized by using functions. For example, you could create a function that takes `n_dots` as input and draws that number of dots on the screen.

5. Try modifying the code to collect reaction time data? Do you respond faster when there are fewer dots?

6. A potential issue with the code at the moment is that dots can overlap. At the moment, we simply generate random positions on the screen without checking where the other dots are located. Write a function to generate *n* dot positions that are non-overlapping, taking into account the `DOT_RADIUS`.

7. Make an option that controls how densely clustered the dots are? Is the task easier if the dots are more densely clustered?

### Analysis activities

1. Try creating your own Jupyter Notebook to document your analyses, and then try the following:

2. How would you extend the analysis to multiple subjects? Can you plot an accuracy curve averaging over participants? Would it perhaps make sense to create a violin plot?

3. Another useful way to look at numerosity estimation data is to plot the correct answer on the *x*-axis against the subject's response on the *y*-axis. This will allow you to see if people tend to over- or underestimate numerosities. Try to write some plotting code to make such a plot.


## Homework

Try to create a new PsychoPy experiment from scratch. Either pick an experiment that you've run before or something you would like to run in the future. If you don't have any ideas, try coding up a classic experiment, like [the Stroop task](https://en.wikipedia.org/wiki/Stroop_effect). Even if you can't implement all parts of the experiment, try to get some parts working (e.g. the instructions screen, the training procedure, the test trials, the data handling, the analysis script, etc...). You might need to do lots of Googling to find out how things are done.
