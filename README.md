# CognitiveParse-2.0
# CognitiveParse

## Project Overview

CognitiveParse is a web-based syntax error detection and correction support system designed for beginner programmers. It helps users analyze Python and C code, detect syntax and logical issues, understand the type of error, and receive guided correction suggestions.

The project combines compiler-design concepts with a practical web interface. Instead of only showing a raw error message, CognitiveParse explains what went wrong, where the issue occurred, and how the user can fix it.

---

## What Does This Project Do?

CognitiveParse allows users to write or paste code into a browser-based editor and analyze it instantly.

The system can:

- Detect syntax errors in Python programs.
- Detect selected logical issues such as:
- Undefined variables
- Division by zero
- Unreachable code
- Unused variables
- Compile and execute C programs.
- Capture and display program output.
- Accept terminal input, similar to stdin in VS Code.
- Classify errors into meaningful categories.
- Provide correction suggestions for common mistakes.
- Store error records in a local database.
- Display analytics such as:
- Total errors
- Python errors
- C errors
- Most common error category
- Error frequency charts
- Daily error trends
- Recent error history

---

## Technologies Used

### Frontend

- **HTML**
  Used to structure the analyzer page and dashboard page.

- **CSS**
  Used to design the user interface, layout, buttons, panels, forms, and dashboard styling.

- **JavaScript**
  Used to handle form submission, call backend APIs, display results dynamically, and draw dashboard charts using canvas.

### Backend

- **Python**
  Used as the main programming language for backend logic, parsing, error handling, and API development.

- **Flask**
  Used to create the web server and API endpoints. Flask connects the frontend with the backend analysis modules.

### Compiler and Parsing Tools

- **Python AST**
  Used to parse Python code and detect syntax errors reliably.

- **PLY**
  Used for lexical analysis and parser integration. It helps demonstrate compiler-design concepts such as tokenization and grammar-based parsing.

- **GCC**
  Used to compile and run C programs, detect C syntax/compiler errors, and return program output.

### Database

- **SQLite**
  Used to store detected errors, categories, timestamps, language type, and suggestions. This data is later used for dashboard analytics.

### Testing

- **Python unittest**
  Used to test API endpoints, parser behavior, logical analyzer, suggestion engine, and report generation.

---

## Why These Technologies Are Used

Flask was chosen because it is lightweight, simple, and suitable for building API-based web applications quickly.

Python AST is used because it provides reliable built-in parsing for Python syntax. It allows the system to detect real syntax errors according to the Python version being used.

PLY is included to connect the project with compiler-design concepts. It demonstrates how lexical analysis and parsing work internally.

GCC is used because it is a standard compiler for C programs and provides real compiler feedback.

SQLite is used because it is simple, file-based, and does not require a separate database server. It is suitable for storing project-level analytics data.

JavaScript canvas is used for dashboard charts because it allows custom visualizations without requiring external chart libraries.

---

## What Makes This Project Different?

Most beginner programming tools only show the default compiler or interpreter error message. These messages can be confusing for students.

CognitiveParse is different because it focuses on explanation and learning. It does not just say that the code is wrong; it tries to explain:

- What type of error occurred
- Where the error occurred
- What token or line caused the issue
- What the user can do to fix it
- How often similar errors are happening

Another important feature is the analytics dashboard. The system tracks error patterns and shows which types of mistakes occur most frequently. This can help students understand their common mistakes and help teachers identify areas where learners need more support.

The project also supports both Python and C, making it more useful for students studying programming fundamentals and compiler design.

---

## Main Features

- Python syntax error detection
- C program compilation and execution
- Logical issue detection
- Error classification
- Correction suggestions
- Terminal input support
- Program output display
- SQLite-based error logging
- Analytics dashboard
- Error category charts
- Daily error trend visualization
- Recent error history table
- Markdown performance report generation
- Unit-tested backend modules

---

## System Architecture

The project follows a simple client-server architecture.

The frontend provides the user interface where users enter code and view results. The backend receives the code, analyzes it, executes it if valid, logs errors, and returns structured results.

Basic flow:

1. User enters Python or C code in the web interface.
2. Frontend sends the code to the Flask backend.
3. Backend checks the selected language.
4. Python code is analyzed using AST, PLY, and logical analysis.
5. C code is compiled and executed using GCC.
6. Errors are classified and suggestions are generated.
7. Results are returned to the frontend.
8. Error data is stored in SQLite.
9. Dashboard uses stored data to show analytics.

---

## API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Opens the main analyzer page |
| `/dashboard` | GET | Opens the analytics dashboard |
| `/analyze` | POST | Analyzes Python or C code |
| `/api/stats` | GET | Returns error category statistics |
| `/api/errors` | GET | Returns recent error records |
| `/api/errors/clear` | POST | Clears stored error records |
| `/api/report` | GET | Returns performance report data |
| `/api/report/markdown` | GET | Returns report in Markdown format |

---

## Project Structure

```text
CognitiveParse/
│
├── backend/
│   ├── app.py
│   ├── parser.py
│   ├── lexer.py
│   ├── ply_parser.py
│   ├── logic_analyzer.py
│   ├── c_analyzer.py
│   ├── executor.py
│   ├── error_handler.py
│   ├── suggestion_engine.py
│   ├── database.py
│   └── performance_report.py
│
├── frontend/
│   ├── index.html
│   ├── dashboard.html
│   ├── style.css
│   └── script.js
│
├── tests/
│   ├── test_api.py
│   ├── test_parser.py
│   ├── test_ply_parser.py
│   ├── test_logic_analyzer.py
│   └── test_suggestion_engine.py
│
├── data/
│   ├── errors.db
│   └── reports/
│
├── requirements.txt
└── README.md

---

