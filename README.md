# ⚡ QuizMaster Pro

A fully client-side, interactive quiz web application with user registration, a 30-minute countdown timer, free question navigation, and a detailed score review — all in a single HTML file with light and dark mode support.

---

## 📸 Overview

QuizMaster Pro is a self-contained quiz application that runs entirely in the browser with no backend or internet connection required (after the initial font load). Users register or log in, pick a category, and attempt 10 randomised questions within a 30-minute time limit. Answers are only revealed after the quiz is submitted or time runs out.

---

## ✨ Features

### 🔐 Authentication
- **User Registration** — name, email, password (min 6 characters), and quiz category selection
- **Login** — returning users can log back in with saved credentials
- Credentials are stored in **localStorage** so they persist across browser sessions

### ⏱ 30-Minute Countdown Timer
- Visible on the sidebar during the quiz
- Turns **yellow** when under 10 minutes remaining
- Turns **red and blinks** when under 5 minutes remaining
- Auto-submits the quiz with a modal alert when time runs out

### 🧭 Free Navigation
- Move between questions using **Previous** and **Next** buttons
- Jump directly to any question using the **dot navigator** in the sidebar
- Dots are colour-coded: answered (purple), current (pink), unanswered (grey)
- Answers can be **changed at any time** before submitting

### 🙈 No Answer Reveal During Quiz
- Selecting an option highlights it — no correct/wrong feedback is shown
- All answers are revealed only **after submission** in the review panel

### 📊 Score Screen
- Circular progress chart showing your percentage score
- Stats breakdown: Correct, Wrong, Skipped, Total
- Time used display
- Personalised performance message based on score

### 📋 Answer Review
- Full question-by-question review after submission
- Correct answers highlighted in green, wrong selections in red
- Filter tabs: **All / Correct / Wrong / Skipped**

### 🌗 Light & Dark Mode
- Defaults to a clean light theme
- Toggle button in the top-right corner on every screen
- Switches instantly across the entire app with smooth transitions

---

## 📚 Quiz Categories

| Category | Questions |
|---|---|
| 🌍 General Knowledge | Capitals, geography, science basics, world records |
| 🔬 Science | Biology, chemistry, physics, astronomy |
| 📜 History | World history, leaders, key events |
| 💻 Technology | Computing, programming, tech companies |

Each session draws **10 questions at random** from the selected category and shuffles their order.

---

## 🚀 Getting Started

### Requirements
- Any modern web browser (Chrome, Firefox, Edge, Safari)
- No installation, no server, no dependencies to install

### How to Run
1. Download or save the `quiz-app.html` file
2. Open it in any web browser by double-clicking it, or drag it into a browser window
3. Register an account and start your quiz

That's it — no npm, no build step, no internet connection needed during the quiz.

---

## 🖥️ Layout & Design

The application uses a **full-page layout** that spans from the top-left to the bottom-right with comfortable padding, rather than a small centred card. Key layout decisions:

- **Auth pages** — two-column layout with a feature hero on the left and the form on the right
- **Quiz page** — sticky sidebar on the left (timer + navigator) with the question panel on the right
- **Score page** — sticky results summary on the left with the full answer review scrollable on the right
- Fully **responsive** — collapses to a single-column layout on mobile and tablet screens

---

## 📁 File Structure

```
quiz-app.html       Single self-contained file — HTML, CSS, and JS all in one
README.md           This file
```

---

## 🔒 Data & Privacy

- All user data (name, email, password, quiz answers) is stored only in your browser's `localStorage`
- No data is sent to any server
- Clearing your browser's site data will remove all stored accounts
- Passwords are stored in plaintext in localStorage — this app is intended for local/educational use and is **not** suitable for production deployment without a proper backend and authentication system

---

## 🎮 How to Play

1. **Register** with your name, email, a password, and choose a category
2. The quiz starts immediately — the **30-minute timer begins**
3. Read each question and **click an option** to select your answer
4. Use **← Previous** / **Next →** to move between questions freely
5. Use the **dot navigator** in the sidebar to jump to any question
6. On the last question, click **Submit Quiz** when you're ready
7. Review your **score and answers** on the results screen
8. Click **Retake Quiz** to try again with a new random set of questions

---

## 🛠️ Customisation

### Adding Questions
Questions are stored as a JavaScript object inside the HTML file. To add more, find the `QUESTIONS` constant and append to any category array:

```javascript
{ q: "Your question here?", opts: ["Option A", "Option B", "Option C", "Option D"], ans: 2 }
```

`ans` is the **zero-based index** of the correct option (0 = A, 1 = B, 2 = C, 3 = D).

### Changing the Timer
Find `const TOTAL_SECS = 30 * 60;` near the top of the script block and change `30` to any number of minutes.

### Adding Categories
Add a new key to the `QUESTIONS` object with an array of at least 10 questions, then add a corresponding `<option>` in the registration `<select>` element.

---

## 🧰 Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | Structure and content |
| CSS3 | Styling, CSS variables for theming, animations |
| Vanilla JavaScript | All quiz logic, timer, localStorage |
| Google Fonts | Syne (headings) + Inter (body text) |

No frameworks, no libraries, no build tools.

---

## 📄 License

This project is free to use for personal and educational purposes.
