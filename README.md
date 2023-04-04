# ansible-jenkins-automation
Setup of an Ansible playbook to automate Jenkins deployment


# Dependences:
- Install Ansible
- Debian Knowleges

# steps:
- we write the Ansible playbook to automate Jenkins deployment.
- And we create the Jenkinsfile in which we define the job executed in the server.


# what is buil in the playbook?
- 1. Installing Java on the Jenkins server (Jenkins requires Java to run)
- 2. Adding the Jenkins Debian repository key and repository to the apt sources list
- 3. Updating the apt cache
- 4. Installing Jenkins using apt
- 5. Starting the Jenkins service and enabling it to start automatically on boot.
- 6. Run the job defined in Jenkinsfile.

 
# playbook execution 
Run the following command:
- ansible-playbook deploy_jenkins.yml -i inventory_file

- **NB** : Replace inventory_file with the path to your Ansible inventory file, and jenkins_server with the name of the host/group where you want to deploy Jenkins

# The Jenkins job explaination:
Jenkins job from the Jenkinsfile XML definition. The createProjectFromXML method takes two parameters: the name of the job to create (in this case, example_job), and the XML definition of the job.

In the XML definition, we're defining a pipeline job that has two stages: Build and Archive. In the Build stage, we're compiling a Java file and packaging it into a JAR file. In the Archive stage, we're archiving the JAR file as a build artifact.

After creating the job, we're scheduling a build of the job with two parameters (ENVIRONMENT and DEPLOY_NOW), just like in the previous example.

Make sure to update the url, user, and password values in the jenkins_script task with the appropriate values for your Jenkins installation.


# Author:
- Mansour KA
