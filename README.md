# Feng

A minimalist, single-file personal website for **Feng Wang**, showcasing education, research, projects, publications, and skills in applied statistics and psychometrics.

## 🌐 Overview

This site is entirely built with **pure HTML, CSS, and JavaScript** — no frameworks, no build tools, and no external dependencies.  
It features a **terminal-style interface**: when you click the top navigation links (Email / Education / Research / Projects / Publications / Skills), the corresponding content is typed line by line into a dark terminal window below.

You can view the live version via GitHub Pages once you enable it in your repository settings.

## 🧩 File Structure

Feng/
├── index.html # Main page with all content, style, and scripts
└── README.md # Project documentation (this file)

css
Copy code

## ✨ Features

- **Single-page portfolio** — all logic in one self-contained HTML file  
- **Typing animation** — terminal-like gradual text rendering  
- **Auto-linking and formatting** — URLs become clickable links; bold text (`**bold**`) turns gold  
- **Keyboard accessible** — focus and ARIA labels for navigation  
- **Responsive and lightweight** — loads instantly with <15 KB total size  

## ⚙️ How It Works

### 1. Content System
All section content is stored inside a JavaScript object called `contentMap`, e.g.:

```js
var contentMap = {
  education: [
    '> open education',
    '',
    '**Boston College** (2023 - 2025)',
    '- M.S. in Applied Statistics and Psychometrics',
    '- Dean\'s Scholarship recipient (All semesters)',
    '',
    '**University of California, Davis** (2017 - 2020)',
    '- B.S. in Psychology'
  ],
  ...
};
Each key corresponds to a menu item (data-target in the HTML). Clicking that link triggers show(key) which prints the text with a typing animation inside the <div id="terminal">.

2. Typing Effect
The animation speed is set to 3ms per character:

js
Copy code
typingTimeout = setTimeout(step, 3);
You can increase it for slower typing (e.g., 15) or set it to 0 for instant rendering.

3. Link Highlighting
After typing finishes, the script:

Converts any http(s) links into clickable hyperlinks (opens in a new tab)

Renders **bold text** in gold

Highlights occurrences of “Feng Wang” or “Wang, F.” in gold for emphasis

4. Auto-Load via URL Hash
Visiting a URL like
https://lyu-meng.github.io/Feng/#skills
automatically opens the “Skills” section on load.

💻 Local Preview
To test locally:

Clone this repo

bash
Copy code
git clone https://github.com/lyu-meng/Feng.git
cd Feng
Open index.html directly in your browser — no server required.

🚀 Deploy to GitHub Pages
Go to Settings → Pages

Under Source, choose Deploy from a branch

Select the main branch and / (root) directory

Click Save, then wait a minute for deployment

Your site will appear at
https://lyu-meng.github.io/Feng/

🧠 Customization Guide
Profile Info — edit <h1> and <p class="tag"> in the HTML

Image — replace the base64 string in the <img> tag with your own photo URL

Links — update LinkedIn / CV URLs inside the <p class="links"> block

Content — edit the contentMap object for each section’s text

Colors & Styles — modify the CSS inside <style> (e.g., .terminal, .head img, .links a)

🧰 Tech Stack
HTML5

Vanilla CSS

Vanilla JavaScript

No frameworks, no npm packages, no build process.

👤 Author
Feng Wang
M.S. Graduate, Applied Statistics and Psychometrics
Boston College
Email: hgwang98@gmail.com | Phone: +1 617-906-1133
LinkedIn | CV

🪪 License
MIT License — feel free to reuse and modify with attribution.
