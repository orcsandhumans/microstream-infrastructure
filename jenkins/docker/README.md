- https://github.com/jenkinsci/helm-charts/tree/main/charts/jenkins
- https://plugins.jenkins.io/

### Plugins

- https://plugins.jenkins.io/pipeline-stage-view/
- https://plugins.jenkins.io/hashicorp-vault-plugin/
- https://plugins.jenkins.io/configuration-as-code/
- https://plugins.jenkins.io/git/
- https://plugins.jenkins.io/kubernetes/
- https://plugins.jenkins.io/workflow-aggregator/
- https://plugins.jenkins.io/junit-realtime-test-reporter/ - TODO

## Docker Jenkins
https://hub.docker.com/_/jenkins

```bash
docker build -t chukhnovmaksym/microstream-infrastructure:latest .
docker run --name microstream-infrastructure -p 8080:8080 -p 50000:50000 -v /var/jenkins_home chukhnovmaksym/microstream-infrastructure:latest
docker push chukhnovmaksym/microstream-infrastructure:tagname
```