---
name: Build and Test
on:
  workflow_dispatch:
permissions:
  contents: read
engine: copilot
network:
  firewall: true
  allowed:
    - defaults
    - github
    - java
    - caffeine.gradle-enterprise.cloud
    - api.foojay.io
---

# Build and Test Java Project

You are an AI agent tasked with building and testing this Java project.

## Instructions

1. First, examine the project structure to determine the build system:
   - Look for `pom.xml` (Maven)
   - Look for `build.gradle` or `build.gradle.kts` (Gradle)

2. This project uses **Gradle** (build.gradle.kts is present).

3. Build the project:
   ```bash
   ./gradlew clean build -x test
   ```

4. Run the tests:
   ```bash
   ./gradlew test
   ```

5. Report the results:
   - If the build succeeds, report success with a summary of the tests run
   - If the build fails, report the error and try to diagnose the issue

## Success Criteria

- The project compiles without errors
- All tests pass (or report which tests failed if any)
