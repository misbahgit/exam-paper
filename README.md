# examstyle LaTeX Package
This is a custom LaTeX style package designed to help streamline the creation of exam papers using the exam document class. This package allows easy configuration of headers, footers, question numbering, and other exam details like subject code, maximum marks, and duration.

## Features
- Commands to set exam metadata (e.g., subject code, paper code, exam type).
- Macros for easy insertion of questions, including optional marks display.
- Auto-numbering of questions with optional "OR" separator for alternative questions.
- Predefined layout for exam headers and notes.
## Requirements
### The package requires the following LaTeX packages:

- amsmath
- enumitem
- geometry
Additionally, you should use the exam class for your document.

## Installation
Save the examstyle.sty file in the same directory as your main.tex document.
Include the style file in your LaTeX document using:
\usepackage{examstyle} % Include the custom style file

Usage
Step 1: Set up the Document
In your main .tex document, use the exam class and load the customexamstyle package:

```latex
\documentclass[11pt,addpoints]{exam}
\usepackage{examstyle}
Step 2: Define Exam Details
Use the following commands to set up exam-specific details:

\setpapercode{<code>}: Set the paper code.
\setsubjectcode{<code>}: Set the subject code.
\setsubjectname{<name>}: Set the subject name.
\setmaxmarks{<marks>}: Set the maximum marks.
\setduration{<duration>}: Set the exam duration.
\setsession{<session>}: Set the academic session.
\setexam{<exam>}: Set the exam type (e.g., Midterm, Final).
\setsemester{<semester>}: Set the semester.
\setbranch{<branch>}: Set the branch or faculty.
\settype{<type>}: Set the exam type (e.g., Theory).
```
Example:

```latex
Copy code
\setpapercode{XYZ123}
\setsubjectcode{MTH101}
\setsubjectname{Mathematics}
\setmaxmarks{100}
\setduration{3 Hours}
\setsession{2023-2024}
\setexam{Final}
\setsemester{1st}
\setbranch{Science}
\settype{Main} % Supplementary
\setfor{For Kids}% any message can be printed in the exam paper headings or may be left blank
```
## Step 3: Insert Exam Header
To insert the exam header with metadata like subject name, session, and instructions, use:

```latex
\qheader
This command will generate a header section at the top of the first page, including all the details you defined in Step 2.
```
## Step 4: Add Questions
To add questions, use the \regularquestion command, it is the main question. To add parts specify using \part You can optionally specify points for each question.

```latex
\begin{questions}
    \regularquestion[5]{What is 2 + 2?}
    \regularquestion{Fill in the blanks}
    \begin{patrs}
    \part[1]Computer is a/an \bank device.
    \part[2]\blank{4} is called the Father of Computers.
    \end{parts}
\end{questions}
```
## Step 5: Use the "OR" Separator (Optional)
For questions with optional choices, you can add the "OR" separator using the \OR command. \OR can be used between regularquestions as well as parts.

```latex
\begin{questions}
    \regularquestion{Explain Newton's first law of motion.}
    \OR
    \regularquestion{Explain Newton's second law of motion.}
\end{questions}
```

## Additional Information
- Blank Space: Use \blank[width] to create a blank space for short answers or Fill in the blanks. If a width is specified it will leave a blank space of the length otherwise the default width is 2 cm.
- Question Numbering: The \regularquestion command automatically increments question numbers, and \questionlabel adds "Q" before each question number.
- Custom headerfooter: The header displays the type of paper, page number, paper code. Footer automatically displays moderation lines, the total number of questions, and space for examiner signatures.
