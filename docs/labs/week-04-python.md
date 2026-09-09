# Week 4 Lab: Human + AI Literature Screening

## What this lab is about

Today, your group will use the **abstracts you already collected** to ask one research-methods question:

> **Can an AI model help us decide which articles are relevant to our research question?**

The goal is **not** to learn or memorize the Hugging Face or pandas code. The code is provided. Your job is to **run it, inspect the output, compare it with human judgment, and decide when the AI is useful or wrong.**

### Not required for the Block 1 exam

You do **not** need to memorize `pipeline()`, pandas/DataFrame commands, Hugging Face syntax, or the AI-classification code in this lab.

You **should** understand the research logic:

**Research question → Human judgment → AI judgment → Compare → Validate**

---

## 1. Start with the work your group already completed

Your group should already have:

- One research question
- 3 peer-reviewed article abstracts per person
- About 12–15 abstracts total
- One combined `.csv` file
- At least these two columns: `Group Member` and `abstract`

Do **not** find a new set of abstracts for this lab.

---

## 2. Human judgment comes FIRST

Before running the AI model, return to the **3 abstracts you personally contributed**.

For each abstract, privately choose one judgment:

- **Clearly relevant** — directly helps answer your research question
- **Possibly relevant** — related, but the connection is incomplete or uncertain
- **Probably unrelated** — does not really help answer your research question

Write down your judgments before looking at the AI results. **Do not change your original judgment after seeing the AI prediction.**

---

## 3. Open Google Colab

Open a new Google Colab notebook. You will copy and run the code below.

### Code A — Install and import the tools

> **Just run this cell. You do not need to memorize it.**

```python
!pip -q install transformers

import pandas as pd
from google.colab import files
from transformers import pipeline
```

In plain English: **Get the tools we need.**

---

## 4. Upload your group's CSV

### Code B — Upload and open your file

```python
uploaded = files.upload()
filename = next(iter(uploaded))

df = pd.read_csv(filename)
df.columns = df.columns.str.strip()

df.head()
```

In plain English: **Upload our file → open it as a table → show the first few rows.**

Check that you can see your abstracts. Your file must contain a column named `abstract`.

---

## 5. Tell the notebook your research question

### Code C — CHANGE ONLY the text between the quotation marks

```python
research_question = "How does social media coverage influence fans' perceptions of athletes?"

print(research_question)
```

Replace the example with **your group's research question**. Keep the quotation marks.

---

## 6. Load the AI model

### Code D — Just run this cell

```python
classifier = pipeline(
    "zero-shot-classification",
    model="facebook/bart-large-mnli"
)
```

The first run may take a few minutes because Colab has to download the model.

In plain English: **Load an existing model that can compare text with categories we provide.**

---

## 7. Try ONE abstract first

### Code E — Create the three screening categories

```python
candidate_labels = [
    f"clearly relevant to the research question: {research_question}",
    f"possibly relevant to the research question: {research_question}",
    f"probably unrelated to the research question: {research_question}"
]
```

### Code F — Ask the model about the first abstract

```python
abstract = str(df.loc[0, "abstract"])

result = classifier(
    abstract,
    candidate_labels,
    hypothesis_template="This abstract is {}."
)

print("ABSTRACT:")
print(abstract)
print("\nAI'S TOP JUDGMENT:")
print(result["labels"][0])
print("\nMODEL SCORE:")
print(round(result["scores"][0], 3))
```

Stop here and discuss:

1. What judgment did the model make?
2. Do you agree?
3. What words or ideas in the abstract may have influenced the judgment?
4. Remember: **a high score is model confidence, not proof that the judgment is correct.**

---

## 8. Run the same procedure on ALL abstracts

### Code G — Just run this cell

```python
def screen_abstract(text):
    text = str(text)
    result = classifier(
        text,
        candidate_labels,
        hypothesis_template="This abstract is {}."
    )
    top_label = result["labels"][0]

    if top_label.startswith("clearly relevant"):
        return "Clearly relevant"
    elif top_label.startswith("possibly relevant"):
        return "Possibly relevant"
    else:
        return "Probably unrelated"


df["AI Judgment"] = df["abstract"].apply(screen_abstract)

df[["Group Member", "abstract", "AI Judgment"]]
```

**You do not need to understand every line.** Read the overall logic:

> For each abstract → ask the same model → use the same categories → save the AI judgment.

That is the research idea of **systematic repetition**.

---

## 9. Compare HUMAN vs. AI

Return to the **3 abstracts you personally contributed**.

For each one, complete this table:

| Group Member | Abstract | Human Judgment | AI Judgment | Agree with AI? | Reason |
| --- | --- | --- | --- | --- | --- |
| Alex | ... | Clearly relevant | Clearly relevant | Yes | The abstract directly studies the exposure and outcome in our question. |
| Maya | ... | Possibly relevant | Probably unrelated | No | The model may have missed an indirect connection to our outcome. |

Your **Reason** is the most important part. Explain what evidence in the abstract supports your decision.

---

## 10. Find ONE interesting disagreement

As a group, choose one case where the human and AI judgments differ—or one case where you almost disagreed.

Be ready to explain:

- Your research question
- The human judgment
- The AI judgment
- Why the disagreement may have happened
- What you would do next as the researcher

Possible explanations include:

- The abstract is genuinely ambiguous
- Your definition of relevance is too broad or too vague
- Important information is missing from the abstract
- The model focused on the wrong words
- The human reviewer interpreted the research question differently

---

## 11. Save the AI results

### Code H — Run this cell

```python
df.to_csv("week4_ai_results.csv", index=False)
files.download("week4_ai_results.csv")
```

In plain English: **Save the table → download a copy.**

---

# Assignment 2 Deliverable

Submit **one agreement table per group** on Blackboard.

Your table should include:

| Group Member | Abstract | Human Judgment | AI Judgment | Agree with AI? | Reason |
| --- | --- | --- | --- | --- | --- |

Each student is responsible for the rows corresponding to the **3 abstracts they personally contributed**.

The assignment is about your **research judgment**, not your ability to memorize Python.

---

## If you finish early: optional challenge

Ask your group:

> **Would you allow this model to automatically EXCLUDE papers from a real literature review? Why or why not?**

Think especially about a **false exclusion**: the AI says a paper is unrelated, but the paper is actually important.

### Key takeaway

**AI can assist with repetitive screening. The researcher still defines relevance, checks disagreements, and makes the final decision.**
