
# Exercise 2 – CI sobre base del Exercise 1

Este repo extiende el **Exercise 1** (Maven + JUnit + Selenium) agregando **pipeline de CI** con stages:
- **Build** (empaqueta sin tests)
- **Unit Tests** (Surefire, `**/*Test.java`)
- **Integration Tests** (Failsafe, `**/*IT.java` usando Selenium headless)

Pipelines incluidos: `Jenkinsfile`, `.gitlab-ci.yml`, `.github/workflows/ci.yml`.

## Comandos locales
```bash
mvn -B -DskipTests package
mvn -B -DskipITs test
mvn -B verify
```
Sube las **capturas** de `evidence/` al PR o al README de tu repo como evidencia de ejecución.
