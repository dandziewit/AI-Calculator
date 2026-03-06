AI Calculator – Natural Language Math Solver

AI Calculator is a web-based calculator that can solve both traditional math expressions and natural language word problems. I built this project to explore how a system can interpret written math questions, classify the problem type, solve it programmatically, and explain the reasoning step-by-step.

Instead of relying on external AI APIs or machine learning libraries, the system uses a rule-based reasoning engine written entirely in vanilla JavaScript. The engine parses user input, extracts numerical information, determines the type of problem being asked, and routes the request to the appropriate solver.

The goal of the project was to better understand how conversational systems interpret user intent and translate language into structured problem-solving logic.

🔗 Live Demo:
https://dandziewit.github.io/AI-Calculator/

Features
Standard Calculator

Basic arithmetic operations

Parentheses support

Responsive calculator layout

Dark-mode UI

AI Word Problem Solver

The AI solver can interpret natural language math questions and convert them into structured calculations.

Supported problem types include:

Percentage problems

Discounts and price reductions

Rate calculations (wages, cost per item, speed)

Comparison problems (twice, half, more than)

Average / mean calculations

Multi-step arithmetic

Simple equations

Sentence-based arithmetic

Each result also includes:

Step-by-step explanations

Confidence score for interpretation

Stored calculation history

System Architecture

The AI solver follows a structured pipeline that converts natural language questions into mathematical solutions.

User Input
   ↓
Text Preprocessing
   ↓
Number & Keyword Extraction
   ↓
Problem Classification
   ↓
Solver Routing
   ↓
Calculation Engine
   ↓
Explanation Generator
   ↓
Result + Confidence Score
   ↓
History Storage

This pipeline keeps the system modular and makes it easy to add new problem types in the future.

AI Processing Pipeline
1. User Input

The user enters a word problem through the AI input field.

Example:

What is 25% of 200?

The input is passed to the AI solver engine for analysis.

2. Text Preprocessing

The system cleans and standardizes the input before parsing.

This includes:

converting text to lowercase

removing unnecessary punctuation

normalizing spacing

Example transformation:

"What is 25% of 200?"
↓
"what is 25% of 200"
3. Number & Keyword Extraction

The system scans the text to identify relevant data such as:

numbers

percentage indicators

comparison words

rate-related keywords

Example extraction:

numbers = [25, 200]
keywords = ["percent"]

This structured data is used to determine the problem type.

4. Problem Classification

The classifier determines what category of math problem is being asked.

Supported categories include:

Percentage

Rate calculations

Comparisons

Average calculations

Multi-step arithmetic

Linear equations

Fallback arithmetic parsing

Each classification produces a confidence score that represents how certain the system is about the interpretation.

5. Solver Routing

Once the problem type is identified, the system routes the request to a specialized solving function.

Example routing logic:

percentage → solvePercentage()
rate → solveRate()
average → solveAverage()
equation → solveEquation()

Each solver is designed specifically for that problem type.

6. Calculation Engine

The solver performs the mathematical operations required to compute the answer.

Example:

25% of 200
↓
0.25 × 200
↓
50
7. Explanation Generator

After computing the answer, the system generates a human-readable explanation of the solution process.

Example output:

Result: 50

Step 1: Convert 25% to a decimal → 0.25  
Step 2: Multiply the decimal by the value  

0.25 × 200 = 50

This allows the calculator to function as both a problem solver and a learning tool.

Example Queries

The AI solver can handle questions like:

What is 25% of 200?

If someone earns $15 per hour and works 8 hours, how much do they make?

A shirt costs $40. With a 15% discount, what is the final price?

What is twice 50?

What is the average of 10, 20, 30, 40, and 50?
History System

Each solved problem is automatically saved to the calculator's history.

Stored data includes:

original query

calculated result

explanation steps

confidence score

timestamp

The history system uses localStorage, allowing calculations to persist between browser sessions.

Tech Stack

The project intentionally avoids frameworks so the entire logic is transparent.

Frontend

HTML5

CSS3

Logic / AI Engine

JavaScript (ES6)

Storage

Browser localStorage

No external dependencies or APIs are required.

Project Structure
AI-Calculator
│
├── index.html
│   Main application interface
│
├── style.css
│   Layout and responsive styling
│
├── calculator.js
│   Calculator logic and AI solver engine
│
└── README.md
Running the Project Locally

Clone the repository:

git clone https://github.com/dandziewit/AI-Calculator.git

Open the project folder:

cd AI-Calculator

Then open index.html in your browser or run a simple local server:

python -m http.server 8000

Then navigate to:

http://localhost:8000
Why I Built This

I built this project to explore how natural language math problems can be interpreted and solved programmatically. Instead of relying on existing AI services, I wanted to design the reasoning pipeline myself and understand how systems classify user intent and route problems to specialized logic.

The project helped me practice building a full front-end application while also experimenting with rule-based AI design and structured problem solving.

Future Improvements

Possible future expansions include:

More advanced natural language parsing

Algebra and multi-variable equation support

Graphing capabilities

Additional math problem categories

Improved explanation generation

Voice input for spoken math questions

Author

Daniel
GitHub: https://github.com/dandziewit
