As soon as I commit and push my code to the git repo...

There are 4 ways by which Jenkins can pull my latest code and start the CI process

-> Manual Trigger: I myself will go to the Jenkins console and click on run build

-> SCM Polling: You configure in Jenkins, that "Jenkins you have to keep on checking the Git Repo and branch main in every 2/5 mins and as soon as you find a new commit then run the CI build" Jenkins stores the last commit id of master branch using which it ran the CI job and this is compared with the latest state of the git repo

-> Scheduled: I can simply schedule the build to run in every 24 hours... like there is a integration testing job and it takes 4 hours to complete... I will create a nightly job in Jenkins and configure it to run at 2 AM every day using a scheduled trigger

-> Webhook Trigger: The better approach to run the CI pipeline
Git Repo is integrated with Jenkins... and then git repo will now be telling Jenkins that "Hey I have a new commit, go ahead and run the CI pipeline"


-----

Shared Library (DRY concepts) / Template the builds : Do not Repeat yourself..

all the team would generate their own bulky Jenkinsfile

I will create a shared library of NodeJs CICD


now all the teams will reference my shared library in their jenkinsfiles and reuse the same code..

------