1. First step is to deploy docker stack with "docker stack deploy -c sonar.yml sonar"
2. Sonarqube is available on port 9000. I use virtualbox so on NAT card I set port 9999 which aims port 9000 on the virtual machine.
3. In a browser I use localhost:9999.
4. To logi in to SonarQube use login: admin, password: admin. Change the password.
5. Go to your account -> security -> generate USER TOKEN
6. Paste you User TOKEN in scaner.yml
7. Before deploing sonarscanner you need to set sonar-project.properties in code location.
  Example:
  sonar.projectKey=my_project_key
  sonar.projectName=My Project
  sonar.projectVersion=1.0
  sonar.sources=.

9. Launch "docker compose -f scaner.yml up -d"  - it's due to order of starting components, so firstly we deploy sonarqube and then we deploy scanner.
