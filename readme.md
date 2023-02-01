# CI CD Jenkins -> AWS

Give a brief overview of the project.

## Demo

Research how you can create Gifs from screen recordings, demo the following:

- CI
  - Make a change to the project on your feature branch -> push changes to repo
  - Show pipeline running in Jenkins -> Show main branch has been updated
- CD
  - Make a change to the project on your feature branch -> push changes to repo
  - Show pipeline running in Jenkins -> Show ci pipeline triggers build pipeline
  - Show updated instance

Video example: https://gifyu.com/image/SmUIF

_Feel free to add more to the points above_

---

## How have you use Jenkins to add Continuous integration with this project?

Through building a test enviroment in Jenkins that would catch any errors in the code rather than allow them to be pushed to the main branch.

### How did you allow Jenkins access to the Github repo?

We allowed Jenkins access to the github repo during the Jenkins configuration where we used the project's URL.

### How did you get the Github repo to trigger the build?

Allowed Jenkins access to GitHub source management using a private SSH key which we generaterated using ssh-keygen -t rsa and deployed the key in github.
Then connected it using the GitHub webhook.

---

## How have you use Jenkins to add Continuous delivery with this project?

If the test build in CI was succcessful, teh post-build action would trigger the and build the CD project. This would them push the build to the main branch.

### How did you allow Jenkins access to the EC2 instance?

By changing the security group in my EC2 I added the option for "JenkinsDeployment".Following this I connected my private SSH key thorugh enabling SSH agent in EC2.

### How did you get the CI project to trigger the CD build?

Using a post-build action in Jenkins called "build other projects" I was able to trigger a build only if the CI was successful.

---
