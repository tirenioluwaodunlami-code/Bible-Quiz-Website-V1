# Quiz App — Local run & editing Q&A

This folder contains a small static quiz app. Follow these quick steps to serve it locally and edit the easy-quiz questions.

**Files:**
- [Index.html](Index.html) — home page with difficulty selector.
- [quiz-easy.html](quiz-easy.html) — Easy quiz page that loads questions from the Q&A file.
- [easy quiz qna.txt](easy%20quiz%20qna.txt) — Plain-text Q&A file you can edit.

Additional files for other difficulty levels:
- [quiz-medium.html](quiz-medium.html) — Medium quiz page; loads `medium quiz qna.txt`.
- [medium quiz qna.txt](medium%20quiz%20qna.txt) — Plain-text medium Q&A file.
- [quiz-hard.html](quiz-hard.html) — Hard quiz page; loads `hard quiz qna.txt`.
- [hard quiz qna.txt](hard%20quiz%20qna.txt) — Plain-text hard Q&A file.

## Serve the folder locally
Use one of these simple options from a PowerShell terminal in this folder:

Python (built-in):
```powershell
cd "c:\Users\ANT\Documents\Personal Projects\Quiz App"
python -m http.server 8000
# or if your system uses the `py` launcher:
py -3 -m http.server 8000
```

Node (no install required if you have Node/npm):
```powershell
cd "c:\Users\ANT\Documents\Personal Projects\Quiz App"
npx http-server -p 8000
```

VS Code Live Server (GUI):
- Open the `Quiz App` folder in VS Code.
- Right-click `quiz-easy.html` and choose "Open with Live Server" or click the status-bar "Go Live".

Then open in your browser:

- Home: http://localhost:8000/
- Easy quiz: http://localhost:8000/quiz-easy.html

Note: Browsers block fetching local files when you open `file://` URLs directly. Always serve the folder with a local HTTP server for the quiz to load the Q&A file.

## Editing the Q&A file
Edit the `easy quiz qna.txt` file (or the medium/hard Q&A files) to change the quiz content. Format rules (simple and human-friendly):

- Separate each question block with a single blank line.
- First line of a block = the question text.
- Following lines = answer options (one per line).
- Mark the correct answer by prefixing that option with an asterisk `*`.

Repeat the same format for `medium quiz qna.txt` and `hard quiz qna.txt` — each file is used by its matching quiz page.

Example block:
```
What is the first book of the Bible?
*Genesis
Exodus
Leviticus
Numbers

Who built the ark?
*Noah
Abraham
Moses
David
```

Save the file (UTF-8) after editing. Then refresh `quiz-easy.html` in your browser to load the updated questions.

## Troubleshooting
- If the quiz page shows "Loading questions..." or a fetch error, ensure you started a local server as above.
- If you see incorrect highlighting, check the `*` is on the correct option line (no leading spaces before `*`).

If you want a different Q&A format (CSV or JSON) or an admin UI to edit questions, I can add that next.
