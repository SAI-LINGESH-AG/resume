# 🚀 Sai Lingesh R – Dynamic Resume Website

A professional, ATS-optimized resume website with a hidden admin panel for AI-powered job application tailoring.

---

## 📁 Project Structure

```
├── index.html              → Public resume website (GitHub Pages)
├── admin/
│   └── index.html          → Hidden ATS generator (password protected)
├── data/
│   └── resume.json         → Master resume database (edit this!)
└── README.md
```

---

## 🌐 Hosting on GitHub Pages (Free)

1. Create a new **public** GitHub repository (e.g. `resume` or `sai-lingesh-resume`)
2. Upload all files maintaining the folder structure
3. Go to repo **Settings → Pages → Branch: main → / (root)**
4. Your site will be live at: `https://YOUR_USERNAME.github.io/REPO_NAME/`

---

## 🔧 Setup Steps

### 1. Update resume.json
Edit `data/resume.json` and fill in:
- `"location": "YOUR_CITY"` → your actual city
- `"phone": "9698451787"` → already set
- NPTEL cert names and years
- Any additional projects

### 2. Set Admin Password
In `admin/index.html`, find this line:
```javascript
const ADMIN_PASSWORD = 'qwertyuiop1234567890';
```
**Change this to a stronger password before pushing!**

### 3. Add Your OpenAI API Key
- Go to your live site at `/admin`
- Enter password
- Paste your OpenAI API key in the API Key field
- It's stored only in your browser session — never committed to GitHub

---

## 🔐 Security Notes

- **Admin panel**: Not linked from the public site. Only you know `/admin` exists.
- **API key**: Never hardcode in files. Always enter via the admin UI.
- **Password**: Stored in JS source (visible in code). Use a non-obvious password.
- **Email/Phone**: Visible in the public resume. Consider using a mailto link only.

---

## 🎯 Resume Versions

Switch between versions via the topbar or URL parameter:
- `/` → Data Engineer (default)
- `/?role=swe` → Software Engineer
- `/?role=ds` → Data Scientist  
- `/?role=ai` → AI/LLM Engineer

---

## ➕ Adding a New Resume Version

1. Add a new entry in `data/resume.json` under `"versions"`:
```json
"devops": {
  "title": "DevOps Engineer",
  "tagline": "...",
  "summary": "...",
  "top_skills": [...]
}
```
2. Add the version button in `index.html`:
```html
<button class="ver-btn" data-version="devops" onclick="switchVersion('devops')">DevOps</button>
```
3. That's it — fully dynamic, no other changes needed.

---

## 📥 Downloads

- **PDF**: Uses html2pdf.js — exact visual copy of what's on screen
- **DOCX**: Generates a formatted Word-compatible document

---

## 🤖 Admin Panel – ATS Generator

Access at: `yoursite.com/admin`

**3-Agent Pipeline:**
1. **Agent 1** – Analyzes JD, extracts keywords and requirements
2. **Agent 2** – Tailors your resume bullets to match JD language
3. **Agent 3** – Writes a personalized cover letter

Outputs: Tailored Resume + Cover Letter + ATS Score + Keyword Analysis
