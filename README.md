# Petclinic-beta
Project Created to store open score pet clinic beta 

Version Control Tools :<b> GIT </b><br>
Build Tool : <b>Maven</b><br>
Static Code Analysis : <b>SonarQube</b><br>
Unit Tests: <b>Junit</b><br> 
Artifact Management Tool : <b>Jforg Artifactory </b><br>
Docker Registry : <b>Jforg Artifactory </b><br>
Integration test : <b>Selenium / Cucumber for Jenkins  </b><br>
CI tool : <b>Jenkins  </b><br>
CD :<b> Jenkins Pipeline  </b><br>
Deployment Infra :<b> AWS/GCP/Azure  </b><br>
Monitoring :<b> Cloud watch / New relic  </b><br>

<b>Setup Jenkins :  </b><br>
<code> 
cd Jenkins
docker build -f JenkinsDockerfile -t petclinic:v1 .
docker run -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):$(which docker) -p 8080:8080 petclinic:v1
</code>

<b> DSL pipeline </b> <br> 
Created a Jenkins pipeline which will be do a code checkout from Github and then do a maven build taking artifactory as reference for binary management. <br>
It will execute static code analysis and create a docker build & store it in Registry <br>
Then image can be deployed to any of the env as per requirement. <br>Sharing the deployment Lifecycle in the doc. 	
