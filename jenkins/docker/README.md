- https://github.com/jenkinsci/helm-charts/tree/main/charts/jenkins
- https://plugins.jenkins.io/

### Docker Jenkins
https://hub.docker.com/_/jenkins

```bash
docker build -t chukhnovmaksym/microstream-infra-jenkins:latest .
```

```bash
docker run --name microstream-infra-jenkins -p 8080:8080 -p 50000:50000 -v /var/jenkins_home chukhnovmaksym/microstream-infra-jenkins:latest
```

```bash
docker push chukhnovmaksym/microstream-infra-jenkins:tagname
```
