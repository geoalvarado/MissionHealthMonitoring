# Mission Health Monitoring (MHM) — Increment 1
## 🗓️ Week 1 Roadmap (Nov 3–7, 2025)
### 🎯 Focus: GitHub Setup & Version Control

**Goal:**  
Initialize the project repository, commit your Spring Boot base project, and establish a professional Git workflow (branches, PRs, and documentation).

---

### 🔧 Step-by-Step Plan

#### **Day 1–2: GitHub Repository Setup**
1. Create a new repository named `MissionHealthMonitoring` on GitHub.  
   - Visibility: `Public` (recommended for portfolio visibility).  
   - Description: *Cloud-native drone telemetry monitoring system.*  
2. Initialize with a `.gitignore` for **Java + Maven** and a **README.md**.  
3. Add a license — **Apache 2.0 License** (ideal for open-source projects).  
4. Clone the repo locally:  
   ```bash
   git clone https://github.com/<your-username>/MissionHealthMonitoring.git
   ```

#### **Day 3: Connect Local Project to GitHub**
1. Move your Spring Boot project (from Weeks 1–2) into the cloned folder.  
2. Initialize Git tracking and push the project:  
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Spring Boot base project"
   git branch -M main
   git remote add origin https://github.com/<your-username>/MissionHealthMonitoring.git
   git push -u origin main
   ```

#### **Day 4–5: Branching & Pull Requests**
1. Create a feature branch:  
   ```bash
   git checkout -b feature/readme-update
   ```
2. Update `README.md` with project overview and setup instructions.  
3. Commit and push the changes:  
   ```bash
   git add README.md
   git commit -m "Updated README with project overview"
   git push origin feature/readme-update
   ```
4. Open a Pull Request (PR) on GitHub and merge it into `main`.

#### **Day 6–7: License & Documentation**
1. Add your **Apache 2.0 License** file (via GitHub template).  
2. Create a `docs/` folder with:  
   - `setup_guide.md` — installation steps, dependencies, and structure.  
   - `changelog.md` — versioning starting at `v0.1.0`.  
3. Push these files and optionally create a **GitHub Project board** for tracking.

---

### ✅ Deliverables
- [ ] GitHub repo named `MissionHealthMonitoring`  
- [ ] `.gitignore` for Java + Maven  
- [ ] Base Spring Boot project committed  
- [ ] `README.md` written and pushed  
- [ ] `LICENSE` file added  
- [ ] Example PR merged from a `feature/*` branch  
- [ ] `docs/` folder with setup guide and changelog  

---

### 📚 Learning Resources
| Topic | Resource |
|--------|-----------|
| Git & GitHub Basics | [GitHub Docs – Hello World Guide](https://docs.github.com/en/get-started/quickstart/hello-world) |
| Git Branching | [Atlassian Git Branching Guide](https://www.atlassian.com/git/tutorials/using-branches) |
| Writing Good READMEs | [Make a README (GitHub Guide)](https://www.makeareadme.com/) |
| Licenses Explained | [Choose a License](https://choosealicense.com/) |
| Markdown Syntax | [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) |

---

### ✅ Weekly Checklist
- [ ] Repository created and connected to local project  
- [ ] `.gitignore` file added  
- [ ] `README.md` written and pushed  
- [ ] License file added  
- [ ] Feature branch and PR tested  
- [ ] Docs folder initialized  

---
