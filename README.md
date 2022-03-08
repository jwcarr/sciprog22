# Scientific Programming: A Crash Course

Welcome to the Scientific Programming course. My name is Jon Carr and I am a postdoc in Davide Crepaldi's lab. I will be your guide to programming over the next four weeks — I look forward to meeting you all soon! This document outlines how I plan to run the course and what you need to do in preparation.


## Organizational Details

The course will be in-presence in Room 139 on Tuesdays and Thursdays over the next four weeks. However, I will also open a Zoom session for people who are not able to attend in person. Nevertheless, I would encourage you all to attend the class in person because you will be able to learn a lot by talking to the people around you and it will be easier for me to help you with individual problems.

Although I will do a little bit of lecturing, the class will mostly be very interactive with lots of practical exercises and independent working. It is therefore important that everyone has access to a laptop computer. I also think it's important for you to use your own daily computer (rather than a random computer in a lab) because then you can get things set up in a way that works well for you and you can use a computer that is familiar.

Although this course is intended for beginners, I'm sure that you all have a diverse range of backgrounds and experiences. For some people, the pace might be too fast; for others, the pace might be too slow. I will try my best to adapt the course depending on your collective needs and interests. If you find the pace too fast, please try to do lots more practice at home; coding is a skill that takes a lot of time to develop. If you find the pace too slow, please use the time in class to dig more deeply into a particular topic.


## Syllabus

My aim with this course is to be relatively broad rather than deep. I would like to cover a variety of different programming languages, paradigms, and applications, as well as more theoretical issues relating to programming practices in science. I hope to give you a broad picture of the options available to you, so that you can feel confident exploring particular areas more deeply by yourself. That being said, I also want to make sure that you have a solid grounding in the core concepts of programming before you progress to more advanced topics.

We will start with Python, which is great general-purpose programming language. The language is pretty friendly, which makes it relatively easy to learn the basic concepts. However, in a few weeks, I also want to introduce the R language, which is very important in statistics, and also some web programming. Please also feel free to tell me stuff that you would like to learn about – I certainly don't know everything, but I'll try to adapt the material accordingly.

At the moment, this is the schedule I have in mind:

1. Tue Feb 15, 10:00–12:00 – Fundamentals

2. Thu Feb 17, 10:00–12:00 – Going Abstract

3. Tue Feb 22, 10:00–12:00 – Good Housekeeping

4. Thu Feb 24, 10:00–12:00 – The Scientific Stack

5. Tue Mar 01, 13:00–15:00 – Building Experiments

6. Thu Mar 03, 13:00–15:00 – Online Experiments

7. Tue Mar 08, 13:00–15:00 – Intro to R

8. Thu Mar 10, 13:00–14:00 – Open-Science and Best Practices


## Software Installation

Before attending the first class, please try to get your computer set up with a working Python installation and the Jupyter Notebook package. Sometimes it can be tricky to get things set up correctly, but I will be available to help you during the first class in case of any problems.

The easiest way to install everything is to use Anaconda: https://www.anaconda.com/products/individual This is a special distribution of Python that includes many scientific packages, including Jupyter Notebook. Once you've installed Anaconda you should be able to run the following command in the terminal or command prompt:

```bash
jupyter notebook
```

This should open a browser window with the Jupyter Notebook interface. Note that, although this looks like a website, it is actually a website running locally on your computer. If you're still finding it difficult to open Jupyter Notebook, check this link, which shows a few different options: https://pythonforundergradengineers.com/opening-a-jupyter-notebook-on-windows.html

### Alternative installation options

The Anaconda distribution is quite large, so if you prefer to be more minimalist, an alternative option is to install the official "vanilla" version of Python: https://www.python.org Once this is installed, you will then need to install the Jupyter Notebook package by running this command:

```bash
pip install notebook
```

Once it has finished installing, you should be able to launch Jupyter as above:

```bash
jupyter notebook
```

If you use Linux or Mac, Python is installed by default as part of the operating system, so it's also possible to use that directly. Alternatively, you may already have a Python installation from previous projects you've worked on. If you go down this route, I would suggest you first create a new virtual environment, so that the packages you install do not conflict with other stuff you might be doing:

```bash
mkdir sciprog22
cd sciprog22
python3 -m venv venv
source venv/bin/activate
pip install notebook
jupyter notebook
````

If this looks a bit scary, don't worry, I can help in class.

### Last resort: Web version

Finally, if you encounter major issues getting stuff installed, you can also use the web version of Jupyter Notebook from here: https://jupyter.org/try This is not a good long-term solution, but you will at least be able to follow along with the course.
