# 🎉 Day 34 – Python Bootcamp Project: Quizzler App

This project is a **Quiz App** built with Python 🐍, `tkinter` for the GUI, and the **Open Trivia DB API** 🎲.
It asks the user True/False questions and keeps track of the score. ✅❌

---

## ✨ Features

* 📡 Fetches **10 True/False coding questions** from the Open Trivia DB API.
* 🖼️ Interactive GUI built with **tkinter**.
* ✅ **True/False buttons** with feedback (green for correct, red for wrong).
* 📊 Score tracking displayed in real-time.
* ⏳ Automatic next question after answering.

---

## 📂 Project Structure

```
📁 Quizzler-App
│── data.py
│── main.py
│── question_model.py
│── quiz_brain.py
│── ui.py
│── 📁 images
│     ├── true.png
│     └── false.png
```

### 🔹 `data.py`

Handles fetching questions from the **Open Trivia DB API**:

```python
import requests

parameters = {
    "amount": 10,
    "type": "boolean",
    "category": 18,
}
response = requests.get("https://opentdb.com/api.php", params=parameters)
question_data = response.json()["results"]
```

---

### 🔹 `main.py`

The **entry point** of the app:

* Builds the question bank.
* Initializes `QuizBrain` and `QuizInterface`.
* Prints final score in the console.

---

### 🔹 `question_model.py`

Defines the **Question class** 📝:

```python
class Question:
    def __init__(self, q_text, q_answer):
        self.text = q_text
        self.answer = q_answer
```

---

### 🔹 `quiz_brain.py`

Handles the **quiz logic**:

* Tracks question number & score.
* Provides next question text.
* Checks user answers.
* Uses `html.unescape()` to clean special characters from API questions.

---

### 🔹 `ui.py`

The **Graphical User Interface (GUI)** 🎨:

* Displays questions on a canvas.
* Shows score at the top.
* Has **True/False buttons** with images.
* Gives instant feedback (background turns green/red).
* Disables buttons at the end of the quiz.

---

## 🖼️ Images

* `true.png` → Green checkmark button.
* `false.png` → Red cross button.

---


## 🎯 What I Learned (Day 34)

* How to make **API calls** in Python using `requests`.
* How to design a **GUI app with tkinter**.
* How to **connect multiple files/modules** in a Python project.
* Using **HTML unescape** to handle special characters.
* Structuring a real-world project with multiple files and an image folder.

---

