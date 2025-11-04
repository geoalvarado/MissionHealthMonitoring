# 🚀 MHM Increment 1 – Week 3 Roadmap  
**Sprint:** Week 3 — *Spring Boot Deep Dive*  
**Dates:** November 10–16, 2025  
**Focus:** Building and understanding Spring Boot controllers, services, and dependency injection.  
**Deliverable:** `TelemetryController` responding with mock telemetry JSON.

---

## 🎯 Sprint Goal
Gain intermediate-level understanding of the Spring Boot framework, focusing on how controllers and services communicate within a layered architecture.  
At the end of this week, your REST API should return a **mock telemetry payload** at `/telemetry/test`.

---

## 🧱 Learning Objectives
- Understand **dependency injection** and how **Spring Beans** work.  
- Create and connect a `Controller` and `Service` layer.  
- Learn about common Spring annotations:
  - `@RestController`
  - `@Service`
  - `@GetMapping`
  - `@Autowired`  
- Learn to manage dependencies through `pom.xml`.  
- Build and test a REST endpoint locally.

---

## 🗂️ Project Tasks Breakdown

### **Day 1–2: Environment Review & Theory**
1. Review your Spring Boot folder structure:
   ```
   src/main/java/com/mhm/hellotelemetry/
     ├── controller/
     ├── service/
     ├── model/
     ├── MhmApplication.java
   ```
2. Read:
   - [Spring Boot Official Docs – Core Concepts](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/)
   - [Dependency Injection in Spring](https://spring.io/guides/gs/consuming-rest/)
3. Add to `pom.xml`:
   ```xml
   <dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-starter-web</artifactId>
   </dependency>
   <dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-devtools</artifactId>
       <scope>runtime</scope>
   </dependency>
   ```

---

### **Day 3–4: Implement the Telemetry Service Layer**
Create `TelemetryService.java`:
```java
@Service
public class TelemetryService {
    public Map<String, Object> getMockTelemetry() {
        Map<String, Object> telemetry = new HashMap<>();
        telemetry.put("droneId", "MHM-001");
        telemetry.put("status", "OPERATIONAL");
        telemetry.put("battery", 87);
        telemetry.put("altitude", 1200);
        telemetry.put("temperature", 34.5);
        return telemetry;
    }
}
```

---

### **Day 5: Implement the Telemetry Controller**
Create `TelemetryController.java`:
```java
@RestController
@RequestMapping("/telemetry")
public class TelemetryController {

    @Autowired
    private TelemetryService telemetryService;

    @GetMapping("/test")
    public ResponseEntity<Map<String, Object>> getTelemetry() {
        return ResponseEntity.ok(telemetryService.getMockTelemetry());
    }
}
```

Test locally:
```bash
mvn spring-boot:run
curl http://localhost:8080/telemetry/test
```

Expected output:
```json
{
  "droneId": "MHM-001",
  "status": "OPERATIONAL",
  "battery": 87,
  "altitude": 1200,
  "temperature": 34.5
}
```

---

### **Day 6: Testing & Validation**
- Test via **Postman** or browser.  
- Confirm **HTTP 200 OK** response.  
- Validate all keys and values in mock JSON.  
- Modify values to simulate changing telemetry (battery drop, temperature rise, etc.).

---

### **Day 7: Documentation & Wrap-Up**
- Update your project’s `README.md`:
  - Add your endpoint and example response.
  - Include testing instructions (`curl` + Postman).
- Take a screenshot of the working endpoint.
- Add comments throughout your code explaining each annotation.
- Prepare a brief note summarizing what you learned this week:
  > “I now understand how controllers and services interact via dependency injection, and how to expose REST endpoints with JSON payloads in Spring Boot.”

---

## ✅ Deliverables for Week 3
| Deliverable | Description |
|--------------|-------------|
| **TelemetryController.java** | REST controller exposing `/telemetry/test` |
| **TelemetryService.java** | Business logic returning mock telemetry JSON |
| **pom.xml** | Updated with `spring-boot-starter-web` and `devtools` |
| **Test Results** | Verified 200 OK response in browser/Postman |
| **Updated README.md** | Includes endpoint usage and documentation |

---

## 🧭 Next Sprint Preview
**Week 3 (Nov 17–23)** – *GitHub Setup & Version Control*  
You’ll:
- Initialize a GitHub repository  
- Push your Spring Boot project  
- Create a professional `README.md` and `.gitignore`  
- Practice branching and PR workflow  
