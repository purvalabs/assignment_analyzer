EvalMate – AI-Assisted Assignment Evaluation System

A front-end prototype showing how AI can help faculty evaluate student assignments faster and more consistently. Faculty review relevance, completeness and correctness at a glance, get suggested marks and feedback, and keep the final decision.

Prototype note: There is no backend, no authentication and no real AI call. All data is sample data and the AI evaluation is simulated.

Features
Landing page with Faculty Login and Student Login (no real authentication)
Faculty dashboard with total assignments, total submissions, pending evaluations, evaluated submissions and average score, plus recent assignments and evaluation activity
Create Assignment form: title, subject, description, question, maximum marks, key concepts and an editable rubric with a running total
Submissions table with student name, roll number, submission status, date, evaluation status, score and action
AI Evaluation screen (three panels):
Left: question, key concepts, rubric
Centre: the student's answer
Right: relevance, completeness and correctness percentages, overall score, detected and missing concepts, AI feedback
Results table for approved evaluations
Analytics: class averages per criterion and most commonly missed concepts
Settings: demo toggles
Student view: score, criterion breakdown and feedback
Tech Stack
React 18 (UMD build, JSX compiled in the browser with Babel Standalone)
Tailwind CSS (CDN)
Inline SVG icons in the style of Lucide
Mock data only

The whole app is a single file, evalmate.html, so there is nothing to install or build.

Running Locally
Download evalmate.html.
Open it in any modern browser (internet access is needed to load React, Babel and Tailwind from CDNs).
Demo Walkthrough
Click Faculty Login.
Look at the dashboard stats and recent activity.
Open Assignments and review the pre-filled "Supervised Learning Basics" example. Edit the rubric if you like, then click Save Assignment.
Open Submissions and click Aarav Sharma, an already evaluated submission.
In the right panel, review the AI results: 92% relevance, 85% completeness, 90% correctness, 8.7 / 10.
Go back and open Rahul Mehta (pending). Click Run AI Evaluation, watch the analysis steps, then click Approve & Save.
Check Dashboard, Results and Analytics, which update with the new evaluation.
Log out and try Student Login to see the student's feedback view.
How the Score Is Calculated

The overall score follows the rubric weights (out of 10):

Criterion	Marks
Correctness	4
Relevance	2
Completeness	2
Explanation	2

Each criterion's percentage is multiplied by its marks and the results are summed. For example, with correctness 90%, relevance 92%, completeness 85% and explanation 80%: 3.6 + 1.84 + 1.7 + 1.6 = 8.74, shown as 8.7 / 10.

Sample Data

Four students (Aarav Sharma, Priya Verma, Rahul Mehta, Ananya Singh) each have a written answer and a pre-defined evaluation result. Results are revealed only when "Run AI Evaluation" is clicked, to mimic a real AI pipeline.

Connecting a Real AI Backend (Future Work)

To turn this into a real system:

Replace the pre-defined res objects with a call to an LLM or NLP service. Send the question, key concepts, rubric and student answer, and return JSON with relevance, completeness, correctness, detected concepts and feedback.
Add a backend and database (assignments, submissions, evaluations) and real authentication with faculty and student roles.
Support file uploads (PDF/DOCX) with text extraction.
Add faculty mark overrides, export to CSV or PDF, and plagiarism checks.
Add bulk evaluation for entire classes.
Limitations
State resets on page refresh.
Evaluation results are simulated, not generated from the actual text.
Only one assignment (Supervised Learning Basics) has evaluable submissions.
Light theme only.
