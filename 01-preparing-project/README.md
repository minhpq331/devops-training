# Module 1: Preparing project

## First things first

Well, before we start the training, we need to prepare the project. This step is very important because it will be the goal of the training and will keep you from getting lost. Find a product that you REALLY want to build. It can be a personal blog, a portfolio, a web application, or anything else. The important thing is that you should be passionate about it. You will spend a lot of time on this project, so make sure you like it and treat it as your spiritual child.

## Requirements

In order to complete the training, just don't pick a project that is too small or simple. It can be a simple blog, but you will make it world-class. So there are some requirements for the your project:

1. **It should have a backend and a frontend**. The backend should be a RESTful API and the frontend should be a single-page application. You can go with GraphQL if you want, no problem.
2. **Architecture of your project**. It should have at least 3 layers: frontend, backend, and database. You can add more dependencies if you want. It should tell everyone how your project works, what technologies you are going to use, and how they are connected.
3. **The documentation**. Break you architecture into smaller parts and write down how each part works. With database, it should be the data schema and relationships. With backend, it should be the API documentation. With frontend, it should be the mock design of the UI,...
4. **The code**. Read about [12factors](https://12factor.net/) app and try to follow it, maybe from simple things like using environment variables, logging to the stdout, or stateless processes. It will help you to build a scalable and maintainable application.

## Basic instructions

1. **Create separate backend and frontend project on Github**
2. **Follow gitflow or any git working flow** to develop your project. Create a `dev` branch to deploy your project to `dev` environment and a `master` (or `main`) branch to deploy your project to `production` environment. Work on `feature`/`hotfix` branches.
3. **Setup your projects on localhost** with different ports. For example, backend on `localhost:3000` and frontend on `localhost:8080`.
4. **Mind your configurations**. Keep an eye on `.gitignore`, `.dockerignore`, `.env`,... files and make sure you don't commit any sensitive information to your repository or include them in your Docker image in a public path.
5. **Code your project**. If you don't want to start from scratch, you can use any projects you can find on the internet. But remember, you should understand the code and ready to debug it.

## References

- [12factor](https://12factor.net/)
- [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

## Useful Resources

- [Building an Uber Clone](https://jurajmajerik.com/blog/start-here/): An awesome example of preparing project for the training. It should include the architecture of the application and overview of all the features you want to implement.