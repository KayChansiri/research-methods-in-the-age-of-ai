# Week 3 Zoom Lab: Python Research Workflow

## Exploring Headlines with Python

Today, you will practice reading, running, modifying, and explaining simple Python code. The activities use the ideas introduced in class:

* variables and `=`
* text and quotation marks
* `print()` and `len()`
* lists and indexes
* loops and indentation
* `if` and `in`
* string tools such as `.lower()`

The goal is **not to memorize Python syntax** or conduct a real content analysis. The goal is to understand what short pieces of code ask the computer to do and to check whether the output makes sense.

!!! important "Today's Cycle"
    **Predict → Run → Look → Explain → Modify**

---

## Before You Begin

Open a new Google Colab notebook:

[Open Google Colab](https://colab.research.google.com/){ .md-button .md-button--primary }

Rename your notebook:

```text
JOUR701_Week3Lab_YourName
```

At the top, add a **Markdown cell** containing:

```text
Name:
Group number:
Group members:
Assigned task:
```

---

## How the Group Activity Works

There are **eight groups with approximately three students in each group**. Each group will be assigned one task and will have approximately **10 minutes** to work.

### Work Together—but Use Your Own Laptop

This is group work, but **every student should complete the task in their own Google Colab notebook on their own laptop**.

Group members should:

1. read the task together
2. discuss predictions before running the code
3. help one another understand instructions and errors
4. compare outputs
5. discuss the AI-assisted modification
6. make sure everyone can explain the code

Do not have only one person complete the code while everyone else watches. Everyone should type or copy, run, modify, and inspect the code independently.

### Suggested Use of Your 10 Minutes

* **Minutes 1–2:** Read the task and make predictions.
* **Minutes 3–6:** Run and modify the code on each laptop.
* **Minutes 7–9:** Complete the AI-assisted modification.
* **Minute 10:** Decide what your group will explain to the class.

### When Your Group Shares

One group member may share a screen. Other members should be ready to help explain:

1. what the task asked Python to do
2. what the group predicted
3. what code the group ran or changed
4. what output appeared
5. how the group checked the result
6. what the group learned from the AI-assisted modification

---

## Using AI During the Lab

Each task ends with a small modification involving a Python idea that was not directly taught in class. You may use an approved AI assistant to help with that part.

Start with a prompt such as:

```text
I am a Python beginner. Help me make the modification described below.
Use the simplest possible code and explain only the new part in plain English.
Do not change the parts of my code that already work.
```

Then add a Markdown cell to your notebook:

```text
AI prompt I used:

New code AI suggested:

What the new code does:

How I verified the result:
```

!!! warning
    AI-generated code is a proposed solution, not a verified solution. Run it, inspect the output, and decide whether it actually answers the question.

---

# Group 1: Store and Display a Headline

Copy this code into a code cell:

```python
headline = "AI Changes Journalism"
print(headline)
```

### A. Predict and Explain

Before running the code, discuss:

1. Which part is the variable name?
2. What does `=` tell Python to do?
3. Why does the headline need quotation marks?
4. What do you predict will appear under the cell?

Run the code and check your prediction.

### B. Modify the Code

Change the stored headline to `Gamecocks Win Season Opener`. Run the cell again and explain why the output changed.

Then create a second variable called `source` that stores the text `The Daily News`. Print both variables.

### C. AI-Assisted Modification: Print Both on One Line

Ask AI to show you the simplest way to print the headline and source together on one line, separated by a hyphen.

Your intended output is:

```text
Gamecocks Win Season Opener - The Daily News
```

Run the suggestion and verify that both pieces of text appear in the correct order.

---

# Group 2: Retrieve Items from a List

Copy and run this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced",
    "Local reporters test new technology"
]
```

### A. Predict and Retrieve

Before running these lines, predict each output:

```python
print(headlines[0])
print(headlines[1])
print(headlines[2])
```

Run the code and check your predictions.

### B. Modify the Code

1. Write one line that prints the fourth headline.
2. Change the second headline in the list to a headline of your choice.
3. Run your retrieval code again and confirm that the new headline appears.

Complete this explanation:

```text
headlines[0] retrieves the __________ item because Python starts counting at __________.
```

### C. AI-Assisted Modification: Retrieve the Final Item Another Way

Ask AI whether Python can retrieve the final list item without first counting the items. Ask it to explain the new index in plain English.

Run the suggested code and verify that it returns the fourth headline.

---

# Group 3: Count Items in a List

Copy this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced"
]

print(len(headlines))
```

### A. Predict and Explain

Before running the code, discuss:

1. What information is stored in `headlines`?
2. What action does `len()` perform?
3. What output do you predict?

Run the code and check your prediction.

### B. Modify the Code

Add two new headlines inside the square brackets. Run the code again.

Discuss:

1. How and why did the output change?
2. Does `len()` count from zero, or report the total number of items?

### C. AI-Assisted Modification: Add an Item with `.append()`

Ask AI how to use `.append()` to add this headline after the list has already been created:

```text
Students learn Python in research methods
```

Print the list and its new length. Verify that the headline appears once and that the total increases by one.

---

# Group 4: Repeat an Instruction with a Loop

Copy this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced"
]

for headline in headlines:
    print(headline)
```

### A. Predict and Explain

Before running the code, discuss:

1. How many lines of output do you predict?
2. What does `headline` represent during each repetition?
3. Why is `print(headline)` indented?

Run the code and check your prediction.

### B. Modify the Code

Add this unindented line after the loop:

```python
print("Finished")
```

Run the code. Explain why each headline prints once but `Finished` prints only once.

Then temporarily remove the indentation before `print(headline)`. Run the code, read the error, restore the indentation, and confirm that it works again.

### C. AI-Assisted Modification: Number the Headlines

Ask AI for a beginner-friendly way to number the printed headlines `1`, `2`, and `3`. Ask it to explain only the new Python idea.

Run the suggestion. Verify that every headline still appears and that the displayed numbers begin with `1`.

---

# Group 5: Use `if` to Make a Decision

Copy this code:

```python
headline = "AI changes journalism"

if "AI" in headline:
    print("This headline mentions AI")
```

### A. Predict and Explain

Before running the code, discuss:

1. What True/False question is Python checking?
2. Do you expect the message to print?
3. Why is the `print()` line indented?

Run the code and check your answers.

### B. Modify the Code

Change the stored headline to:

```python
headline = "Gamecocks win season opener"
```

Run the code again. Explain why no message appears.

Then change the condition so Python searches for `Gamecocks`. Run it and verify the result.

### C. AI-Assisted Modification: Add an `else`

Ask AI how to make Python print `This headline does not mention AI` when the condition is not true. Ask it to use an `else` statement and explain how `if` and `else` work together.

Test the code with one headline that mentions AI and one that does not. Verify that exactly one message appears for each headline.

---

# Group 6: Combine a List, Loop, and `if`

Copy this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced",
    "Local reporters test new AI tool"
]

for headline in headlines:
    if "AI" in headline:
        print(headline)
```

### A. Predict and Explain

Before running the code:

1. Predict which headlines will print.
2. Identify the line that repeats.
3. Identify the line that checks a condition.
4. Explain why the final line has more indentation.

Run the code and compare the output with your prediction.

### B. Modify the Research Question

Change the code so it prints only headlines containing `music`. Then add this headline to the list:

```text
Music fans discuss new concert venue
```

Run the code again. Verify that the output answers the new question.

### C. AI-Assisted Modification: Count the Matches

Ask AI to modify the original AI-search code so it also counts how many headlines contain `AI`. Ask it to use a simple counter and explain the new lines.

Run the suggestion. Verify the count by manually checking the four headlines yourself.

---

# Group 7: Make a Search Ignore Capitalization

Copy this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "Local reporters test new ai tool"
]

for headline in headlines:
    if "AI" in headline:
        print(headline)
```

### A. Predict and Investigate

Before running the code, predict whether Python will print both headlines that discuss AI.

Run the code and discuss:

1. Which expected headline is missing?
2. What difference do you notice between `AI` and `ai`?
3. Does Python treat uppercase and lowercase letters as identical here?

### B. Modify the Code

Use `.lower()` to make the search ignore capitalization:

```python
for headline in headlines:
    if "ai" in headline.lower():
        print(headline)
```

Run the code and verify that both relevant headlines appear.

Complete this explanation:

```text
The dot tells Python to use the __________ tool that belongs to the current __________.
```

### C. AI-Assisted Modification: Search for Two Possible Words

Ask AI to modify the condition so the code prints a headline when it contains either `ai` or `technology`, regardless of capitalization. Ask it to explain the word `or`.

Add a headline containing `technology`, run the code, and manually verify every match.

---

# Group 8: Debug and Verify a Small Workflow

This code should print only headlines containing `AI`, but it has problems:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "Local reporters test new AI tool"
]

for headline in headlines
if "AI" in headline:
print(headline)
```

### A. Predict the Intended Result

Before running the code:

1. Identify which headlines should print if the code works.
2. Identify the list, loop, condition, and action.

### B. Debug One Problem at a Time

Run the code and read the first error. Fix one problem, run the code again, and continue until the intended headlines appear.

Keep a record in a Markdown cell:

```text
Problem 1:
How we fixed it:

Problem 2:
How we fixed it:

How we verified the final output:
```

### C. AI-Assisted Modification: Request Hints, Not the Whole Answer

If your group becomes stuck, ask AI:

```text
Explain the first remaining problem in this Python code.
Give me one hint, but do not rewrite the full solution.
```

After the code works, ask AI to add one final unindented line that reports `Search finished`. Verify that it appears once, after all matching headlines.

---

# What You Practiced

By the end of the lab, the class should have practiced how to:

* store text with variables
* group text in lists
* retrieve list items with indexes
* count items with `len()`
* repeat instructions with loops
* use indentation to show which instructions repeat
* use `if` and `in` to check a condition
* use `.lower()` to make a search ignore capitalization
* read and respond to simple errors
* modify code for a slightly different research question
* use AI to learn one small new Python idea
* verify AI-generated code by inspecting the output

!!! note
    Different groups will work with different Python ideas. During screen sharing, focus on understanding how each group translated its code into everyday language and verified its result.

