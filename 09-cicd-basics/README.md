# Module 9: CI/CD basics

In this module, you will learn the fundamentals of Continuous Integration and Continuous Deployment (CI/CD). You will create a basic bash script to automate deployments using GitLab CI, and set up both automatic and manual builds for different branches within your project.

## Requirements

Our goal in this module is to create a simple deployment pipeline using GitLab CI. This will involve:

- Writing a bash script to handle deployment tasks
- Configuring GitLab CI to trigger this script automatically upon code changes.
- Setting up different build jobs based on branches, with some triggering automatically and others manually.

## Instructions

1. **Deployment Script:** Create a bash script (e.g., `deploy.sh`) that handles the deployment of your application. Imagine it will do exactly what you do when you need to update your application on the server.
Some tasks you might want to include in the script:
- Pulling the latest code from your repository
- Installing / updating dependencies (like `npm install` or `yarn install`)
- Building the application (if needed)
- Restarting the application to use the updated code

The script for your BE and FE might look different.

2. **GitLab CI Automation:** Configure GitLab CI by creating a `.gitlab-ci.yml` file in your repository's root. Define a deployment stage to do the following tasks:

- SSH into the server using SSH key-based authentication
- Trigger the deployment script

3. **Branch-Specific Builds:** Test the auto deployment on specific branches like `dev`, `staging` or `uat`. Change the auto deployment to manual for `main` or `release` branches to see how it works.

## Important Notes

- **Security:** Be mindful of sensitive information in your scripts and CI/CD configuration. Do not commit credentials to your repository. Use Gitlab CI secrets instead. Never echo that secrets to the console.
- **Zero downtime deployment:** It can be hard to achieve zero downtime deployments with your current setup. But try to find a way to do it through your deployment script. It can help you understand a lot about how your application lifecycle works. At least try to reduce the downtime as much as possible by pulling/install dependencies to a temporary folder before restarting your application.

## Useful Resources

- [How To Set Up a Continuous Deployment Pipeline with GitLab CI/CD on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-continuous-deployment-pipeline-with-gitlab-on-ubuntu#step-6-configuring-the-gitlab-ci-yml-file): Basic tutorial to setup GitlabCI, focus on the ssh part and ignore the docker stuff.
- [Zero Downtime Deployments with PM2](https://medium.com/learnwithrahul/zero-downtime-deployments-with-pm2-93013713df15): Some guide to achieve zero downtime deployments with PM2. This can only apply to your BE Node.js app.
