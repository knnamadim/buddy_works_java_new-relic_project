# Simple Java Project with New Relic Observability

This project demonstrates **how to instrument a Java Servlet with New Relic APM** and track custom metrics for observability purposes. It is based on the Buddy Works sample project ([buddy-works](https://github.com/buddy-works/simple-java-project)) and can be deployed locally or on platforms like Heroku.

---

## Prerequisites

- Java 8+ installed  
- Maven installed  
- A New Relic account with a valid license key  
- New Relic Java Agent ([Download here](https://docs.newrelic.com/docs/apm/agents/java-agent/installation/java-agent-installation))  

---

## Project Structure
src/
└─ main/
└─ java/
└─ works/buddy/samples/
└─ WorksWithHerokuServlet.java
target/
└─ simple-java-project-1.0-SNAPSHOT.jar


- **WorksWithHerokuServlet.java** – Servlet that responds to HTTP GET requests and demonstrates a **custom New Relic metric**.  

---

## Setup Instructions

### 1. Clone the Project
- git clone https://github.com/buddy-works/simple-java-project.git
- cd simple-java-project

## Build the Project
- mvn clean install
  
## Configure the New Relic Java Agent
- Download and extract the agent.
- Edit newrelic.yml
  app_name: SimpleJavaProject
  license_key: YOUR_NEW_RELIC_LICENSE_KEY
  
- Run the Project with New Relic: java -javaagent:/path/to/newrelic.jar -jar target/simple-java-project-1.0-SNAPSHOT.jar

- Test the Servlet: curl http://localhost:8080/workswithheroku

## Creating a Dashboard in New Relic
1. Log in to New Relic → Dashboards → Create a dashboard.
2. Add widgets for:
    Request throughput
    Response times
    Error rates
    Custom metric Custom/Requests
3. Optionally, create alerts for high error rates or slow response times.

---

## Next Steps
- Deploy to Heroku or another cloud environment.
- Add more custom metrics (e.g., API call counts, latency buckets).
- Create charts to visualize business impact, which can be used in a demo or use case panel for interviews.
