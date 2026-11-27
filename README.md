
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
