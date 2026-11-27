from pathlib import Path
import zipfile, math

base = Path("/mnt/data/Priyanka_GitHub_Profile_80")
base.mkdir(exist_ok=True)

readme = """<div align="center">

# 👋 Hi, I'm Priyanka!
### M.Tech CSE Student | Python | AI & Machine Learning

<p>
  <img src="https://img.shields.io/badge/LEARNING%20%26%20PRACTICE-80%25-8B5CF6?style=for-the-badge" />
  <img src="https://img.shields.io/badge/STATUS-Consistently%20Learning-06B6D4?style=for-the-badge" />
</p>

</div>

---

## 👩‍💻 About Me

- 🎓 Pursuing M.Tech in Computer Science Engineering.
- 🎓 B.Tech in Artificial Intelligence and Data Science.
- 💡 Interested in programming, AI, Machine Learning and software development.
- 🌱 Learning, practicing and training through hands-on projects.

## 🛠️ Skills — Learning & Practice Progress

*My current learning and practice progress is 80% across the skills shown below.*
These circles represent self-reported learning/practice progress, not a verified proficiency or exam score.

<div align="center">
  <img src="./skills.svg" alt="Circular learning and practice progress: 80 percent for each skill" width="720" />
</div>

## 🎓 Learning Journey

mermaid
flowchart TD
    A["B.Tech - AI & Data Science"] --> B["M.Tech - Computer Science"]
    B --> C["Learn Concepts"]
    C --> D["Practice Skills"]
    D --> E["Apply Through Projects"]


## 📂 Projects

| Project | Area |
|---|---|
| Fake Image Detection using CNN | Deep Learning |
| Student Performance Prediction | Machine Learning |
| Smart Irrigation and Plant Monitoring | IoT |

## 🚀 My Learning Cycle

mermaid
flowchart LR
    A["Learn"] --> B["Practice"]
    B --> C["Build Projects"]
    C --> D["Improve"]
    D --> A


## 📫 Connect

- GitHub: https://github.com/YOUR_USERNAME
- LinkedIn: Add your LinkedIn profile URL

---

<div align="center">
  ⭐ Thanks for visiting my profile!
</div>
"""

skills = [
    ("Python", "#22C55E"),
    ("C Programming", "#38BDF8"),
    ("SQL", "#A78BFA"),
    ("HTML", "#F97316"),
    ("CSS", "#EC4899"),
    ("Machine Learning", "#FACC15"),
]
W, H = 720, 430
r = 43
circ = 2 * math.pi * r
coords = [(120, 145), (360, 145), (600, 145), (120, 335), (360, 335), (600, 335)]
svg = [
    f'<svg xmlns="http://www.w3.org/2000/svg" width="{W}" height="{H}" viewBox="0 0 {W} {H}">',
    '<rect width="100%" height="100%" rx="24" fill="#0B1020"/>',
    '<text x="360" y="38" text-anchor="middle" fill="#F8FAFC" font-family="Arial,sans-serif" font-size="22" font-weight="700">LEARNING &amp; PRACTICE PROGRESS</text>',
    '<text x="360" y="61" text-anchor="middle" fill="#94A3B8" font-family="Arial,sans-serif" font-size="12">Self-reported progress across my skills</text>',
]
for (label, color), (cx, cy) in zip(skills, coords):
    dash = circ * 0.8
    svg += [
        f'<circle cx="{cx}" cy="{cy}" r="{r}" fill="none" stroke="#263247" stroke-width="9"/>',
        f'<circle cx="{cx}" cy="{cy}" r="{r}" fill="none" stroke="{color}" stroke-width="9" stroke-linecap="round" stroke-dasharray="{dash:.2f} {circ:.2f}" transform="rotate(-90 {cx} {cy})"/>',
        f'<text x="{cx}" y="{cy+7}" text-anchor="middle" fill="#FFFFFF" font-family="Arial,sans-serif" font-size="20" font-weight="700">80%</text>',
        f'<text x="{cx}" y="{cy+67}" text-anchor="middle" fill="#E2E8F0" font-family="Arial,sans-serif" font-size="14" font-weight="600">{label}</text>',
    ]
svg.append("</svg>")

(base / "README.md").write_text(readme, encoding="utf-8")
(base / "skills.svg").write_text("\n".join(svg), encoding="utf-8")
zip_path = Path("/mnt/data/Priyanka_GitHub_Profile_80_Percent.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    z.write(base / "README.md", "README.md")
    z.write(base / "skills.svg", "skills.svg")

print(f"Created {zip_path}")
print("Files: README.md and skills.svg")
