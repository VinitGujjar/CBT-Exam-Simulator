# CBT Exam Simulator

A lightweight browser-based CBT exam simulator for practice tests, previous year papers, and self-made quizzes.

## Features

- One-question-at-a-time exam interface
- Timer with auto-submit
- User-defined marks per correct answer
- User-defined negative marks per wrong answer
- Previous/Next navigation
- Mark for review
- Question palette with attempted, unattempted, visited, and review status
- Random question order
- Random option order
- Manual question paste
- TXT/CSV import
- Auto Arrange Text for messy pasted/imported questions
- Browser-only PDF text extraction
- Local PDF.js files for better offline support
- Question preview and missing-data checker before starting
- Practice mode and exam mode
- Mistake notebook for wrong questions
- Recent test history saved in the browser
- Light mode and dark mode
- Auto, mobile preview, and desktop preview layouts
- Detailed result page with score, accuracy, attempted/unattempted count, correct answer, user answer, and explanation
- Section-wise performance analytics
- Save result as PDF using the browser print dialog

## Question Format

```text
Section: Physics
Que 1
What is the SI unit of power?
A) Newton
B) Joule
C) Watt
D) Pascal
Answer: C
Explanation: Power is measured in watt. One watt equals one joule per second.
```

`Section:` and `Explanation:` are optional, but adding them improves analytics and revision.

## PDF Import

Use **Extract from PDF** to pull text from a PDF into the question box. The app works best with text-based PDFs. Scanned image PDFs may need OCR first.

The extractor tries to handle both common formats:

- answers written near the question
- answer keys or detailed solutions written at the end of the PDF

After extraction, review the questions once before starting the test because PDF layouts can mix lines, tables, formulas, or options.

## AI Prompt for Creating Questions

```text
Create MCQ questions for CBT Exam Simulator in exactly this format:

Section: [topic name]
Que 1
Question text?
A) option 1
B) option 2
C) option 3
D) option 4
Answer: A/B/C/D
Explanation: short explanation of the correct answer

Rules:
- Start every question with a question marker: Que 1, Que 2, Que 3, and so on.
- Use only four options: A, B, C, D.
- Do not put blank lines inside one question set.
- Keep Question, A, B, C, D, Answer, and Explanation on consecutive lines.
- For statement/assertion questions, do not add a blank line between the question and statements.
- Put exactly one blank line only after the full Explanation line, before the next question starts.
- Do not use bullets, tables, markdown headings, or extra numbering.
- Do not add introductory lines like "Here are the questions", "Sure", or "Below is the formatted quiz".
- Keep the answer as only one letter after "Answer:".
- Make explanations exam-focused and concise.
```

## AI Prompt for PDF Extraction

```text
Extract all MCQs from this PDF and convert them into this exact format:

Section: [subject/topic/chapter name]
Que 1
Question text?
A) option 1
B) option 2
C) option 3
D) option 4
Answer: A/B/C/D
Explanation: solution or reason for the correct answer

Important rules:
- Start every question with a question marker: Que 1, Que 2, Que 3, and so on.
- If answers or solutions are at the end of the PDF, match them with the correct question number.
- Preserve technical terms, units, formulas, and year tags like [SSC-JE-2023].
- Do not mix two questions together.
- Do not include page headers, footers, watermarks, or page numbers.
- If a question has a table or assertion-reason format, rewrite it clearly as plain text.
- Do not put blank lines inside one question set.
- Keep Question, A, B, C, D, Answer, and Explanation on consecutive lines.
- For statement/assertion questions, do not add a blank line between the question and statements.
- Put exactly one blank line only after the full Explanation line, before the next question starts.
- Do not add introductory lines like "Here are the questions", "Sure", or "Below is the formatted quiz".
- Return only the final formatted questions, no extra explanation.
```

## Run Locally

Open `index.html` in any modern browser.

## GitHub Pages

1. Upload this folder to a GitHub repository.
2. Go to `Settings > Pages`.
3. Choose `Deploy from branch`.
4. Select the `main` branch and `/root`.
5. Open the published GitHub Pages URL.

## Project Structure

```text
cbt-exam-simulator/
  index.html
  help.html
  README.md
  sample-questions.txt
  screenshots/
  vendor/
    pdfjs/
```

## Important

Do not put Gemini, OpenAI, or any API key directly inside `index.html`. For AI explanations or OCR later, use a small backend so the key stays private.
