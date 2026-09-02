# Week 3 Zoom Lab: Python Research Workflow

## Exploring Headlines with Python

Today, we will practice the exact Python ideas introduced in class:

* storing information in a variable
* grouping text in a list
* retrieving one item with an index
* repeating an instruction with a loop
* using `if` to make a simple decision
* using `.lower()` to work with capitalization
* reading output and deciding whether it makes sense

The goal is **not to memorize Python syntax** or complete a real content analysis. The goal is to read short pieces of code, explain them in everyday language, run them, and check the result.

!!! important "Today's Goal"
    Use this cycle throughout the lab:

    **Predict → Run → Look → Explain**

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
Group members:
```

During the lab, one person may share a screen, but everyone should explain predictions and help check the output.

---

# Part 1: Read and Run One Instruction

Copy this code into a **code cell**:

```python
headline = "AI Changes Journalism"
print(headline)
```

### Before You Run It

Discuss these questions with your group:

1. Which part is the variable name?
2. What does `=` tell Python to do?
3. Why does the headline need quotation marks?
4. What do you predict will appear under the code cell?

### Run and Check

Run the cell. Did the output match your prediction?

Now change the headline to:

```text
Gamecocks Win Season Opener
```

Run the cell again and confirm that the output changed.

### Explain It in Plain English

Complete this sentence in a Markdown cell:

```text
The first line tells Python to...
The second line tells Python to...
```

---

# Part 2: Store Several Headlines in a List

Copy and run this code:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced"
]

print(headlines)
```

### Read the Code

Discuss:

1. What is the name of the variable?
2. What do the square brackets `[ ]` mean here?
3. How many headlines are in the list?
4. Why does each headline have quotation marks?

### Make One Change

Add this fourth headline inside the list:

```text
Local reporters test new AI tool
```

Run the cell again. Check that all four headlines appear.

---

# Part 3: Retrieve One Headline

Python starts counting positions at `0`:

```text
0 = first item
1 = second item
2 = third item
3 = fourth item
```

Before running the code, predict the output of each line:

```python
print(headlines[0])
print(headlines[1])
print(headlines[2])
```

Run the code and check your predictions.

### Your Turn

Write one line of code that prints the **fourth** headline.

!!! hint
    Use the variable name, square brackets, and the position number.

### Explain It

Complete this sentence in a Markdown cell:

```text
headlines[0] retrieves the __________ headline because Python starts counting at __________.
```

---

# Part 4: Repeat an Instruction with a Loop

Copy this code, but **predict what it will print before running it**:

```python
for headline in headlines:
    print(headline)
```

### Translate the Code

Read it in everyday language:

```text
For each __________ in the group called __________,
show me that __________.
```

Run the code and inspect the output.

### Notice the Indentation

The spaces before `print(headline)` tell Python that the instruction belongs inside the loop. It should repeat for every headline.

Now run this version:

```python
for headline in headlines:
    print(headline)

print("Finished")
```

Discuss:

1. Which line repeats?
2. Which line runs only once?
3. How does the indentation help you tell the difference?

---

# Part 5: Use `if` to Print Only Matching Headlines

A researcher wants to find headlines that contain the text `AI`.

First, examine one headline:

```python
headline = "AI changes journalism"

if "AI" in headline:
    print("This headline mentions AI")
```

### Before You Run It

Discuss:

1. What question is Python checking?
2. Do you expect the message to print? Why?

Run the code and check your answer.

Now change the headline to:

```python
headline = "Gamecocks win season opener"
```

Run the code again. Explain why no message appears.

---

# Part 6: Combine a List, Loop, and `if`

Return to this list:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced",
    "Local reporters test new AI tool"
]
```

Now copy this code:

```python
for headline in headlines:
    if "AI" in headline:
        print(headline)
```

### Predict → Run → Look → Explain

1. Predict which headlines will print.
2. Run the code.
3. Compare the output with your prediction.
4. Explain what each line does in everyday language.

Complete this explanation in a Markdown cell:

```text
The loop takes one __________ at a time from __________.
The if statement checks whether __________ appears in that headline.
The print statement runs only when __________.
```

---

# Part 7: Make the Search Ignore Capitalization

Replace the final headline with this version:

```python
headlines = [
    "AI changes journalism",
    "Gamecocks win season opener",
    "New music festival announced",
    "Local reporters test new ai tool"
]
```

Notice that the last headline now contains lowercase `ai`.

Run the earlier search again:

```python
for headline in headlines:
    if "AI" in headline:
        print(headline)
```

### What Happened?

Did Python find both AI headlines? Why or why not?

Now use `.lower()` so capitalization does not matter:

```python
for headline in headlines:
    if "ai" in headline.lower():
        print(headline)
```

### Explain the Dot

Complete this sentence:

```text
headline.lower() tells Python to use the __________ tool that belongs to the current __________.
```

---

# Part 8: Use AI to Explain—Then Verify

Ask an approved AI assistant:

```text
Explain this code one line at a time in plain English for someone learning Python:

for headline in headlines:
    if "ai" in headline.lower():
        print(headline)
```

Add a Markdown cell containing:

```text
AI prompt I used:

One part of the explanation that helped me:

How my group verified the explanation:
```

Remember: **AI-generated explanations and code are proposed answers.** You still need to run the code and inspect whether the result makes sense.

---

# Optional Challenge: Change the Research Question

Only begin this section after completing Parts 1–8.

Use the same list of headlines, but change the code so it prints only headlines containing the word `music`.

Then add this new headline to your list:

```text
Music fans discuss AI-generated songs
```

Run your code again and check whether the new result makes sense.

---

# Screen Sharing

When your group shares, briefly show:

1. one prediction your group made
2. the code you ran
3. the output
4. one line translated into everyday language
5. one way you checked that the result made sense

You do not need a perfect solution. A surprising output or error is useful if your group can explain what you tried and what you learned.

---

# What You Practiced

By the end of this lab, you should have practiced how to:

* use a variable to store text
* use a list to store several pieces of text
* retrieve one list item using its position
* repeat an instruction with a loop
* recognize why indentation matters
* use `if` and `in` to check a condition
* use `.lower()` to make a text search ignore capitalization
* translate short code into everyday language
* predict, run, inspect, and verify output
* use AI to support understanding without giving up verification

