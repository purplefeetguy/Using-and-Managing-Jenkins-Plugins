
## Run Jenkins

Built from [this Dockerfile](../jenkins/old/Dockerfile), standard Jenkins 2.204 install plus setup of old plugin:

```
docker run -d -p 8083:8080 --name jenkins3 sixeyed/psod-jenkins:2.204.4-old

<!-- docker run -p 8083:8080 -d --network jenkins -v plugins3_jenkins_home:/data --name jenkins-controller-plugins3 jenkins/jenkins:lts -->
```

Browse to http://localhost:8083 & sign in with:

- username `psod`
- password `psod`

## Check the warnings

Multiple security warnings:

- Same UI if Jenkins is out of date

- Click through to _Plugin Manager_

- Multiple old versions

Two buttons:

- _Check Now_ checks with the plugin server for latest versions

- _Download and restart_ does that; no checking for compatibility

Check warning box again:

- Follow link to CVE

- "password stored in plain text"

- ... need to update, need to take risk