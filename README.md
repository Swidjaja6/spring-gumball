# spring-gumball ci/cd example

### This example demonstrates the following two GitHub Workflows.

* https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-gradle

* https://github.com/google-github-actions/setup-gcloud/tree/master/example-workflows/gke

### Build Dependencies

* Gradle 5.6
* JDK 11

## CI Workflow

Had problem intially with the gradlew, which did not exist. I checked the directories and I corrected it putting everything in the spring-gumball folder. In my machine, I had it nested in another spring-gumball folder while trying to pull the project. I corrected this error and I fixed my results. 

![CIWorkflow](https://github.com/Swidjaja6/spring-gumball/blob/main/images/CIWorkflowPt1.png)

## CD Workflow

I ran a total of 4 versions of my GKE Gumball. The first is 1.0; the problem I ran into was that the key in GKE SA KEY was not in the correct format. The error stated "unexpected token in JSON at position 0". This was because I pasted the key directly. Instead of that, I put in the JSON file that was downloaded to my computer upon creating the key. 

The second error was the permissions. I had to remake my service to add roles to the email associated with the github account. I put the Owner role which let me bypass this error.

The last error I got was with the name of the GKE Project parameter. I had the name of my project cmpe172 placed as my parameter. However, this was instead to be my project ID which I found on my project description on Cloud. This was corrected and my project finally ran without any problems and I deployed gumball to the cloud. 

### GCP Service Setup
![GCPServiceAccount](https://github.com/Swidjaja6/spring-gumball/blob/main/images/GCPServiceAccount.png)

![JSONKey](https://github.com/Swidjaja6/spring-gumball/blob/main/images/JSONServiceAccountKey.png)

![GithubActionSecrets](https://github.com/Swidjaja6/spring-gumball/blob/main/images/GithubActionSecrets.png)

### Workflows done
![Workflows](https://github.com/Swidjaja6/spring-gumball/blob/main/images/Workflows.png)

![goodOne](https://github.com/Swidjaja6/spring-gumball/blob/main/images/successfulWorkflow.png)

### GKE 
![Cluster](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeCluster.png)

![Deployment](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeDeployment.png)

![Service](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeService.png)

![IngressSetUp](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeIngressSetup.png)

![Ingress](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeIngress.png)

![Gumball](https://github.com/Swidjaja6/spring-gumball/blob/main/images/gkeGumball.png)
