```yaml

    configScripts:
      github-config: |
        credentials:
          system:
            domainCredentials:
              - credentials:
                  - stringCredentials:
                      scope: GLOBAL
                      id: "GitHubToken"
                      secret: ""  # Reference the Kubernetes Secret
                      description: "GitHub API Token for authentication"
        unclassified:
          githubpluginconfig:
            configs:
              - name: "InHouse GitHub EE"
                apiUrl: "https://api.github.com"
                credentialsId: "GitHubToken"
                manageHooks: false
```