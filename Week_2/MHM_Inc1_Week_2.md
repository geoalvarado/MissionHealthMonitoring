# Increment 1 — Week 2 (VS Code)

**Objective (End‑of‑Week Outcome):** A Spring Boot service runs locally and `GET /ping` returns `System Operational`.

**What you’ll use:** macOS Terminal • VS Code • Java 17 (Temurin) • Spring Boot • Maven Wrapper • curl (or VS Code REST Client)

---

## 1) System Setup (Java 17 LTS)

> If you already have **Homebrew**, skip the first line; otherwise install from https://brew.sh

```bash
# (Optional) Install Homebrew if needed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Java 17 (Temurin)
brew install --cask temurin17

# Verify Java 17
java -version
/usr/libexec/java_home -V

# Set JAVA_HOME for current shell
export JAVA_HOME=$(/usr/libexec/java_home -v 17)

echo $JAVA_HOME

# Persist it for future shells
printf '\n# Java 17 for MHM\nexport JAVA_HOME=$(/usr/libexec/java_home -v 17)\n' >> ~/.zshrc
```

**Expected:** `java -version` shows `openjdk version "17.x"` and `JAVA_HOME` points to a `jdk-17` path.

---

## 2) Install VS Code + Extensions

1. Install VS Code: https://code.visualstudio.com
2. Launch once, then install extensions:

```bash
# Core Java tooling pack
code --install-extension vscjava.vscode-java-pack

# Spring Boot tools (Dashboard, Actuator integration)
code --install-extension vmware.vscode-spring-boot

# Optional QoL
code --install-extension humao.rest-client     # VS Code REST Client
code --install-extension redhat.vscode-yaml    # YAML support
code --install-extension gabrielbb.vscode-lombok # Lombok annotations
```

> If `code` isn’t found, open VS Code → Command Palette (⇧⌘P) → **Shell Command: Install 'code' command in PATH**.

---

## 3) Generate the Spring Boot Project

Open https://start.spring.io and configure:

- **Project:** Maven • **Language:** Java • **Spring Boot:** latest stable
- **Group:** `com.mhm` • **Artifact:** `hello-telemetry`
- **Dependencies:** `Spring Web` (optional: `Spring Boot DevTools`)
- Click **Generate**, unzip, then **File → Open** the folder in VS Code. When prompted, **Trust** the workspace.

**Project layout you should see**
```
hello-telemetry/
 ├─ src/main/java/com/mhm/hellotelemetry/
 │   └─ HelloTelemetryApplication.java
 ├─ src/main/resources/
 │   └─ application.properties
 ├─ pom.xml
```

---

## 4) Implement the `/ping` Endpoint

Create `src/main/java/com/mhm/hellotelemetry/PingController.java`:

```java
package com.mhm.hellotelemetry;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class PingController {
    @GetMapping("/ping")
    public String ping() {
        return "System Operational";
    }
}
```

(Optional) in `src/main/resources/application.properties` set an explicit port:

```properties
server.port=8080
```

---

## 5) Run the Service

**Option A – Maven Wrapper (recommended first run)**
```bash
./mvnw spring-boot:run
```

**Option B – VS Code Debugger**
- Press **F5** → choose **Java**
- Select `HelloTelemetryApplication` when prompted

**Expected log snippet:** `Started HelloTelemetryApplication ...` and `Tomcat started on port(s): 8080`.

---

## 6) Verify the Endpoint

**curl**
```bash
curl -i http://localhost:8080/ping
# HTTP/1.1 200 ...
# System Operational
```

**VS Code REST Client (optional)**

Create `requests.http` at project root:
```http
### Health ping
GET http://localhost:8080/ping
```
Open the file and click **Send Request** above the `GET` line.

---

## 7) Hot Reload (DevTools, optional but nice)

If you didn’t include DevTools during project generation, add to `pom.xml`:

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-devtools</artifactId>
  <scope>runtime</scope>
  <optional>true</optional>
</dependency>
```

Then restart the app once. Changes to code/resources will trigger quick restarts.

---

## 8) Git Init (for your Increment 1 repo)

```bash
cd hello-telemetry

# Basic .gitignore for Maven/Java
cat > .gitignore << 'EOF'
# Maven
/target/
!.mvn/wrapper/maven-wrapper.jar

# IDEs
.idea/
*.iml
.vscode/

# OS
.DS_Store
EOF

git init
git add .
git commit -m "Week 2: VS Code setup + /ping endpoint"
```

---

## 9) Troubleshooting Cheatsheet

| Symptom | Likely Cause | Fix |
|---|---|---|
| `java -version` shows 1.8 or 21 | Wrong JDK active | `export JAVA_HOME=$(/usr/libexec/java_home -v 17)` then restart terminal/VS Code |
| VS Code shows unresolved symbols | Java server not started | Command Palette → **Developer: Reload Window**; run `./mvnw -q -DskipTests package` once to prefetch deps |
| Port 8080 already in use | Another process bound to 8080 | Set `server.port=8081` in `application.properties` |
| `command not found: code` | Shell helper not installed | VS Code → Command Palette → **Shell Command: Install 'code' command in PATH** |
| `mvnw` permission denied | No exec bit on wrapper | `chmod +x mvnw` and retry |

---

## 10) Acceptance Criteria (check these off)

- [ ] Java 17 installed and `JAVA_HOME` set
- [ ] VS Code installed with **Java Pack** and **Spring Boot** extensions
- [ ] Project `hello-telemetry` opens and builds with Maven Wrapper
- [ ] App runs locally and logs show Tomcat started
- [ ] `GET /ping` returns **System Operational** (HTTP 200)
- [ ] Initial commit pushed to your repo (optional remote)

---

## 11) Optional Stretch (10–20 min)

- Add a second endpoint `GET /telemetry/test` that returns JSON:

```java
@GetMapping("/telemetry/test")
public Map<String, Object> test() {
    return Map.of("status", "ok", "ts", System.currentTimeMillis());
}
```

- Create a `requests.http` entry to hit `/telemetry/test`.
- Skim Spring’s official guides on REST controllers and configuration to prep for Week 2.

---

### Notes for MHM Increment 1 Tracking
- This file documents Week 2 deliverables and steps tailored for VS Code.
- Keep it in your project docs folder (e.g., `docs/increment-1/Week_1_VSCode_Setup.md`).
- Use the checklist above as your **Definition of Done** for Week 2.

