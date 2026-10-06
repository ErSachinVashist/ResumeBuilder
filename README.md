# Resume Builder

A dynamic HTML resume that loads content from a JSON data file.

## Files Structure

```
doc/
├── index.html    # Main resume page (renders all sections)
├── data.json     # Resume content (edit this to update resume)
├── styles.css    # Styling
└── README.md     # This file
```

## How to View

Due to browser security (CORS), you need to serve the files via a local server:

**Option 1: Using Python**
```bash
cd doc
python3 -m http.server 8080
# Open http://localhost:8080
```

**Option 2: Using Node.js**
```bash
cd doc
npx serve
# Open the URL shown in terminal
```

**Option 3: VS Code Live Server**
- Install "Live Server" extension
- Right-click `index.html` → "Open with Live Server"

## How to Edit Content

### Edit via data.json (Recommended)

Open `data.json` and modify the content. The structure is:

```json
{
  "personal": {
    "name": "Your Name",
    "title": "Your Title",
    "summary": "Your summary...",
    "contact": {
      "email": "email@example.com",
      "phone": "+1234567890",
      "location": "City, Country",
      "linkedin": "linkedin.com/in/yourprofile"
    }
  },
  "coreCompetencies": [
    {
      "title": "Category Name",
      "skills": "Skill 1 • Skill 2 • Skill 3"
    }
  ],
  "leadershipHighlights": [
    {
      "label": "Highlight Title",
      "description": "Description of the highlight."
    }
  ],
  "experience": [
    {
      "title": "Job Title",
      "company": "Company Name",
      "date": "Start – End | Location",
      "summary": "Role summary (optional, set to null if not needed)",
      "achievements": [
        "Achievement 1",
        "Achievement 2"
      ]
    }
  ],
  "education": [
    {
      "degree": "Degree Name",
      "school": "School Name",
      "date": "Start - End",
      "location": "Location"
    }
  ]
}
```

### Edit Directly on Page (Quick Tweaks)

The page is editable in the browser:
1. Open the page in browser
2. Click anywhere to edit text
3. Press Enter to add new lines
4. Make adjustments before printing

**Note:** Browser edits don't save permanently. For permanent changes, edit `data.json`.

## How to Print as PDF

1. Open the page in Chrome/Edge
2. Press `Ctrl + P` (or `Cmd + P` on Mac)
3. Set "Destination" to "Save as PDF"
4. Set "Margins" to "None" or "Minimum"
5. Enable "Background graphics"
6. Click "Save"

## How to Customize Styling

Edit `styles.css` to change:

- **Colors:** Search for `#3d8b8b` (teal accent) or `#4a5568` (dark gray)
- **Fonts:** Change `font-family` in the `body` selector
- **Spacing:** Adjust `margin`, `padding`, `gap` values
- **Font sizes:** Modify `font-size` values

### Key CSS Classes

| Class | Description |
|-------|-------------|
| `.resume-container` | Main container width and shadow |
| `.header` | Header section styling |
| `.contact-bar` | Contact information bar |
| `.section` | Each resume section |
| `.section-header` | Section title with icon |
| `.experience-item` | Job entry styling |
| `.competency-group` | Competency category |
| `.leadership-list` | Leadership highlights list |
| `.education-row` | Education items layout |

## Adding/Removing Sections

### Add a New Experience Entry

In `data.json`, add to the `experience` array:

```json
{
  "title": "New Job Title",
  "company": "Company Name",
  "date": "Start – End | Location",
  "summary": "Role description",
  "achievements": [
    "Achievement 1",
    "Achievement 2"
  ]
}
```

### Add a New Competency Category

In `data.json`, add to `coreCompetencies`:

```json
{
  "title": "New Category",
  "skills": "Skill 1 • Skill 2 • Skill 3"
}
```

### Remove an Entry

Simply delete the object from the respective array in `data.json`.

## Tips

- Use `•` (bullet) to separate skills in competencies
- Keep achievements concise but impactful
- Use action verbs at the start of achievements
- Quantify results where possible (e.g., "reduced by 70%", "led team of 16")
