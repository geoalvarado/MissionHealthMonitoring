# Increment 1 Detailed Checklist – Learning & Environment Setup

**Project:** Mission Health Monitoring (MHM)  
**Increment Duration:** November – December 2025  
**Goal:** Establish full local development environment and deliver a functional “Hello Telemetry” REST API.

---

## ✅ Week 1 (Nov 3–9) — Java + Spring Boot Foundations

**Objectives:**
- [ ] Install **Java 17** and verify installation (`java -version`).
- [ ] Install and configure **IntelliJ IDEA** or **VS Code**.
- [ ] Create first **Spring Boot** project using **Spring Initializr**.
- [ ] Understand basic project structure (`Controller`, `Service`, `Repository` packages).
- [ ] Implement a `/ping` endpoint that returns `"System Operational"`.
- [ ] Test endpoint locally using `curl` or Postman.
- [ ] Add `application.properties` and configure default port (8080).

**Deliverable:** Functional “Hello Telemetry” REST API responding locally.

---

## ✅ Week 2 (Nov 10–16) — Spring Boot Deep Dive

**Objectives:**
- [ ] Learn about **dependency injection** and Spring Beans.  
- [ ] Create a **TelemetryController** with `/telemetry/test` endpoint returning mock JSON.  
- [ ] Implement a **TelemetryService** layer that returns static telemetry data.  
- [ ] Understand and use **`@RestController`**, **`@Service`**, and **`@GetMapping`** annotations.  
- [ ] Update `pom.xml` to include dependencies: `spring-boot-starter-web`, `spring-boot-devtools`.  
- [ ] Test endpoint in browser and Postman.  

**Deliverable:** `TelemetryController` responding with mock telemetry payload.

---

## ✅ Week 3 (Nov 17–23) — GitHub Setup & Version Control

**Objectives:**
- [ ] Create new **GitHub repository** named `MissionHealthMonitoring`.  
- [ ] Initialize project with `.gitignore` for Java + Maven.  
- [ ] Add and commit base Spring Boot project.  
- [ ] Create a **README.md** describing the project’s purpose and goals.  
- [ ] Add an **Apache 2.0 License** (or your preferred one).  
- [ ] Practice Git branching workflow: `main`, `feature/*`, and PR creation.  

**Deliverable:** Active GitHub repository with base project committed and documented.

---

## ✅ Week 4 (Nov 24–30) — Docker & Local Environment

**Objectives:**
- [ ] Install **Docker Desktop** and verify setup (`docker --version`).  
- [ ] Create a **Dockerfile** to containerize the Spring Boot app.  
- [ ] Build Docker image: `docker build -t mhm-api .`  
- [ ] Run container locally: `docker run -p 8080:8080 mhm-api`.  
- [ ] Access app via browser/Postman to confirm operation.  
- [ ] Document Docker steps in README.  

**Deliverable:** Spring Boot API running inside Docker container.

---

## ✅ Week 5 (Dec 1–7) — AWS CLI Configuration

**Objectives:**
- [ ] Install **AWS CLI v2** and configure credentials (`aws configure`).  
- [ ] Create an **IAM user** with limited permissions (S3, EC2, RDS).  
- [ ] Verify CLI access: `aws s3 ls`, `aws ec2 describe-instances`.  
- [ ] Create an **S3 bucket** for project artifacts.  
- [ ] Explore **Elastic Beanstalk** and **RDS** consoles in AWS Management Console.  
- [ ] Note IAM roles and permissions for future use.  

**Deliverable:** AWS CLI configured and verified with test commands.

---

## ✅ Week 6 (Dec 8–14) — Integration & Testing

**Objectives:**
- [ ] Write **unit tests** for `/telemetry/test` endpoint using **JUnit 5**.  
- [ ] Integrate Dockerized API with AWS CLI environment.  
- [ ] Test API endpoint locally in Docker container.  
- [ ] Validate REST responses using Postman (status code 200, JSON response).  
- [ ] Refactor code based on test outcomes.  
- [ ] Create simple **logging** output for requests and responses.  

**Deliverable:** Locally tested, validated, and containerized Spring Boot API.

---

## ✅ Week 7–8 (Dec 15–31) — Documentation & Wrap-Up

**Objectives:**
- [ ] Write complete **README.md** setup guide (Java, Spring, Docker, AWS CLI).  
- [ ] Create **architecture diagram** using Draw.io or Lucidchart.  
- [ ] Record screenshots of successful endpoints and Docker runs.  
- [ ] Create `Increment1_Summary.md` report.  
- [ ] Review Increment 1 checklist and mark completed tasks.  
- [ ] Prepare backlog for **Increment 2 (Core Backend Development)**.  

**Deliverable:** Completed documentation and signed-off Increment 1 milestone.

---

## 🏁 Final Increment 1 Deliverables

- [ ] “Hello Telemetry” REST API in Docker  
- [ ] Verified AWS CLI setup  
- [ ] GitHub repo with documented setup and commits  
- [ ] Architecture diagram (PNG/PDF)  
- [ ] Increment 1 summary report  

---

**Sign-off:**  
🧑‍💻 Developer: Geovannie Alvarado  
📅 Date Completed: _______________________  
🔖 Increment Status: ☐ In Progress ☐ Completed  
