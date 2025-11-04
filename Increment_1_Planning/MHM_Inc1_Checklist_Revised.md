# Increment 1 Detailed Checklist – Learning & Environment Setup

**Project:** Mission Health Monitoring (MHM)  
**Increment Duration:** November – December 2025  
**Goal:** Establish full local development environment and deliver a functional “Hello Telemetry” REST API.

---

## ✅ Week 1 (Nov 3–9) — GitHub Setup + Base Spring Boot Project

**Objectives:**
- [ ] Install **Java 17** and verify installation (`java -version`).  
- [ ] Install and configure **IntelliJ IDEA** or **VS Code**.  
- [ ] Create a new **GitHub repository** named `MissionHealthMonitoring`.  
- [ ] Initialize repo with `.gitignore`, `README.md`, and license.  
- [ ] Generate a new Spring Boot project via Spring Initializr.  
- [ ] Commit and push base project to GitHub.  
- [ ] Implement a `/ping` endpoint returning “System Operational.”  
- [ ] Test endpoint locally (`curl` or Postman).

**Deliverable:** Functional Spring Boot project pushed to GitHub with basic endpoint.

---

## ✅ Week 2 (Nov 10–16) — Spring Boot Controllers and Services

**Objectives:**
- [ ] Learn dependency injection and Spring Beans.  
- [ ] Create `TelemetryController` with `/telemetry/test` endpoint returning mock JSON.  
- [ ] Implement `TelemetryService` layer for static telemetry data.  
- [ ] Understand and apply `@RestController`, `@Service`, `@GetMapping`.  
- [ ] Add dependencies (`spring-boot-starter-web`, `devtools`).  
- [ ] Test endpoint in browser and Postman.

**Deliverable:** `TelemetryController` returning mock telemetry payload.

---

## ✅ Week 3 (Nov 17–23) — Spring Boot Deep Dive & Version Control Refinements

**Objectives:**
- [ ] Refactor package structure (`controller`, `service`, `repository`).  
- [ ] Add branching model: `main`, `feature/*`.  
- [ ] Open and merge a sample Pull Request.  
- [ ] Review README and update setup instructions.  
- [ ] Introduce logging using `@Slf4j` or `LoggerFactory`.  

**Deliverable:** Refined codebase with clear version control workflow.

---

## ✅ Weeks 4 – 8 remain unchanged
*(Docker, AWS CLI, Integration, Testing, and Documentation sections as before.)*

---

**Sign-off:**  
🧑‍💻 Developer: Geovannie Alvarado  
📅 Date Completed: _______________________  
🔖 Increment Status: ☐ In Progress ☐ Completed
