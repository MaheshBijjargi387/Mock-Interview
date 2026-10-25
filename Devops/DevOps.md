# What is a repository in Git?
->A Git repository is a folder that Git uses to track and manage changes in your project.

# What is the .git Directory?
->.git is a hidden directory that stores Git’s metadata, including the history of our code, commits, branches, and tracking information.

# What is the difference between Git and GitHub?
-> Git tracks and records the history of changes in our code locally. GitHub stores a copy of those commits online and provides a platform for collaboration.

# What is origin in Git?
-> origin is the default name or nickname given to the remote repository, usually on GitHub.

# What is the purpose of the .gitignore file?
->.gitignore is a file used to specify files and folders that Git should ignore. Git will not track those files when we add changes to the repository

# What is a version control system ?
-> A Version Control System is a tool that tracks changes in our code over time. It helps us manage different versions, see the history, and work with other developers.

# What is the Git Workflow?
-> Git workflow is the process of making changes in the working directory, adding them to the staging area, committing them to the local repository, and finally pushing them to the remote repository like GitHub

# How to cannacel from staging area
-> git restore --staged 

#  What is the git push command?
->The git push command is used to upload our local commits to a remote repository

# What is the git pull command?
-> git pull is used to download the latest changes from the remote repository (GitHub) and update your local branch

# what is the git fetch ?
-> git fetch downloads the latest changes from GitHub to your local Git repository

# what is difference between fetch and pull ?
->git fetch → Download changes, don't apply them to your current branch.
git pull → Download changes and apply/merge them into your current branch.


# What is the Difference Between a Fork and a Clone?
-> Fork creates a copy of a repository on our GitHub account, while clone downloads a repository from GitHub to our local computer.

# What does git clone do?
-> The git clone command creates a complete local copy of a remote Git repository, including its commit history, branches, and configuration

# What is the difference between git init and git clone?
-> git init is used to create a new Git repository from an existing local project, while git clone is used to copy an existing remote repository to our local computer.

# What is git add?
-> git add is used to move the changes from the working directory to the staging area.

# What is git status?
-> git status is used to check the current state of your Git repository.

# What is a commit in Git?
->A commit is a saved record of changes in Git. It creates a snapshot of the staged changes and stores them in the local repository with a commit message

# What is the git log Command?
-> git log is used to view the commit history of a Git repository. It shows details like commit ID, author, date, and commit message

# What is the git show Command?
-> git show is used to see the details of a particular commit.

# What is git checkout?
-> it checkout is used to switch between branches or restore files to an earlier version.

# How do you switch branches in Git?
->  git switch <branch-name>

# what is rebase
-> Git rebase is used to move our branch's commits on top of the latest commits from another branch.

# What is the git restore Command?
->git restore is used to undo changes in your working directory or remove files from the staging area.

# What is the purpose of the git clean command?
->git clean is used to delete untracked files and folders from your working directory. Untracked files are files that Git is not tracking yet.

# What is a 'conflict' in git?
->A Git conflict happens when two different changes are made to the same part of a file, and Git cannot decide which change to keep.

# What is the meaning of 'Index' in GIT?
->In Git, the Index is the staging area where we keep the changes that are ready to be included in the next commit

# How do you change the last commit in git?
-> We use git commit --amend to modify the most recent commit, such as adding forgotten changes or changing the commit message

# What differentiates between the commands git remote and git clone?
-> git clone is used to copy an existing remote repository to your computer
   git remote is used to manage or view the connection between your local repository and a remote repository.

# What are the benefits of using a pull request in a project?
->A Pull Request is used to propose changes from one branch to another. It allows team members to review the code, discuss changes, find bugs, and safely merge the code into the main branch

#  What is a Git bundle?
-> A Git bundle is a single file that contains Git repository data, such as commits and branches.

# What is git stash?
->git stash is used to temporarily save your uncommitted changes without committing them
   Later, you can bring your changes back:->git stash pop

#  How do you revert a commit that has already been pushed and made public?
-> If a commit has already been pushed and shared, we use git revert to undo it. It creates a new commit that reverses the changes of the previous commit without deleting the original commit

# Explain the difference between reverting and resetting?
-> git revert undoes a commit by creating a new commit, so it is safe for shared or public history. git reset moves the branch pointer to an earlier commit and can remove commits from the branch history

# What is the difference between git reflog and log?
-> git log → Shows commit history.
   git reflog → Shows the history of HEAD/branch movements.

# What is HEAD in Git?
-> HEAD is a pointer that tells Git where you are currently working.

# How can you delete a remote Git branch?
-> git push origin --delete <branch-name> 

# What is git blame?
-> git blame is used to find out who made each change in a file and when

# what is git diff
-> git diff is used to see what changes you have made but have not committed yet.

# what is git tag
->git tag is used to give a name/label to an important commit, usually for a version or release.

# git cherry-pick
-> git cherry-pick is used to take one specific commit from another branch and apply it to your current branch.

# You made changes, but then realize you are working on the wrong Git branch.
->First, I would check the current branch and the changes using git status. If my changes are not committed, I would safely save them using git stash. Then I would switch to the correct branch, apply the changes using git stash pop, and continue my work there.

# You and another developer modified the same lines of the same file. When you try to merge their branch into yours, Git shows a merge conflict.
->I would first open the conflicted file and understand both changes. Then I would decide which code should be kept or combine both changes correctly. After resolving the conflict, I would test the application, stage the resolved file, and commit the merge.

# You made a commit, but later realize that the commit contains some changes that should not have been included. The commit has not been pushed to GitHub yet.
->I would use git reset to move the commit back and keep my files available. Then I would remove the unwanted changes, stage only the correct files, and create a new commit.

# You accidentally pushed a file containing a database password/API secret to a GitHub repository. You realize it immediately.
->First, I would revoke or rotate the exposed secret immediately, because simply deleting the file is not enough—the secret may still exist in Git history. Then I would remove the secret from the code, add the file to .gitignore if needed, and push the fix. If necessary, I would clean the Git history and inform the team.

# You make a commit and run git push, but GitHub rejects the push with a message like “rejected because the remote contains work that you do not have locally.”
->I would first pull the latest changes from the remote repository, resolve any conflicts if they occur, test my code, and then push again.

# You pushed a commit to a shared GitHub branch, but later discover that the code is causing a bug. Other developers have already pulled the latest changes.
->I would use git revert instead of git reset. Revert creates a new commit that safely undoes the previous commit without changing the shared Git history.

# You are working on a feature, but your manager suddenly asks you to fix an urgent bug on another branch. Your current changes are incomplete and you don't want to commit them yet.
->I would use git stash to temporarily save my uncommitted changes. Then I would switch to the bug-fix branch, fix and commit the bug, and later return to my original branch and use git stash pop to restore my work.

# You intended to push your feature to feature/payment, but accidentally pushed it to feature/order. You realize the mistake after the push.
->First, I would check whether anyone has already pulled the incorrect branch. If not, I would move the changes to the correct branch and remove them from the wrong branch if appropriate. If the branch is shared, I would avoid rewriting its history and coordinate with the team before making changes.

# Your teammate has made 5 commits on their branch, but you need only one specific commit from their work in your branch.
->I would use git cherry-pick with the specific commit ID. This applies only that commit to my current branch without merging all 5 commits.

# Your application was working correctly yesterday, but today you find a bug. There are many commits from different developers, and you don't know which commit introduced the problem.
->I would use git bisect to find the problematic commit. I would mark a known working commit and a known bad commit, and Git will help me check commits between them until I identify the commit that introduced the bug

# You start working in the morning and try to push your changes, but your teammate has already pushed new commits to the same remote branch.
->I would first get the latest changes from the remote branch using git pull. If there is a conflict, I would resolve it, test the application, commit the resolution if needed, and then push my changes.

# You have completed a feature and merged it into main. Your team wants you to clean up the old feature branch.
->I would first confirm that the branch has been successfully merged and is no longer needed. Then I would delete the local branch and the remote GitHub branch.

# You run git status and see a file like application-local.properties as untracked. This file contains your local database credentials and should not be uploaded to GitHub.
->I would not add it to the commit. I would add the file to .gitignore so Git ignores it in future. For sensitive configuration, I would use environment variables or a proper secret-management solution instead of storing credentials in Git.

# You create a Pull Request on GitHub, but GitHub says your branch has merge conflicts with main.
->I would update my branch with the latest main changes, resolve the conflicts locally, test the application, and push the updated branch. Then I would check the Pull Request again to make sure the conflicts are resolved and CI checks are passing.

# You committed your changes with the message fix, but your team follows meaningful commit messages. The commit has not been pushed to GitHub yet.
->I would change the last commit message using git commit --amend. Since the commit has not been pushed, changing the local commit history is safe.

# You find a suspicious line of code in a production-related file. You want to know who changed that particular line and which commit introduced it.
->I would use git blame on that file. It shows the commit and author associated with each line, so I can identify who made the change and then inspect that commit for more details.

# You accidentally reset your branch and now an important commit is no longer visible in git log. You realize you still need that commit.
->I would use git reflog to find the previous commit reference. Once I find the required commit, I can recover it by creating a branch from that commit or resetting my branch back to it.

# You made a commit locally, but now you want to remove the commit while keeping all the code changes so you can modify the code and commit it again properly.
->I would use git reset --soft HEAD~1. It removes the last commit but keeps the changes staged, so I can modify them and create a new commit.

# You create a Pull Request on GitHub. During code review, another developer says your implementation has a bug and asks you to change it.
-> would make the requested changes in the same feature branch, test them locally, commit the changes, and push them to GitHub. The existing Pull Request will automatically update with the new commit.

# Your team is developing a new feature, but suddenly a critical bug appears in production. Your current feature branch contains unfinished work.
->If I have unfinished work and need to urgently fix a production bug, I use git stash to temporarily save my changes, switch to the production branch, fix and push the bug, then return to my feature branch and use git stash pop to restore my work

# Your feature branch is behind main. Your team prefers a clean, linear Git history and does not want unnecessary merge commits.
->I would use git rebase main on my feature branch. This reapplies my feature commits on top of the latest main changes. If conflicts occur, I would resolve them and continue the rebase.

# You and another developer are working on the same feature. Both of you modify the same Java service file, and now you need to combine your work.
->I would first communicate with the developer and understand what each person changed. Then I would update my branch with their latest changes and resolve any conflicts carefully. After resolving, I would run tests to make sure both changes work correctly before pushing and creating/updating the Pull Request.

# You accidentally deleted your local feature branch before pushing all of its commits to GitHub. You realize that some important commits are now missing.
->I would use git reflog to find the commit that the deleted branch was pointing to. Then I would create a new branch from that commit and recover my work.

# You create a Pull Request, but the GitHub Actions CI pipeline fails because some tests are failing.
->I would check the GitHub Actions logs to identify the exact failure. Then I would reproduce the issue locally, fix the code or tests, run the tests again, and push the fix to the same branch. The Pull Request CI will run again automatically.

# You had local uncommitted changes. You ran git pull, and now your working files look different from what you had before. You are worried that your work is lost.
->First, I would not make more changes blindly. I would check git status and inspect the recent Git history. If my changes were committed or stashed earlier, I can recover them from Git history or git stash. If necessary, I would use git reflog to find previous states and recover the work.

# You joined a new project. Your team lead gives you the GitHub repository URL, but when you try to clone it, GitHub says “Repository not found” or “Permission denied.”
->First, I would check whether I am logged in with the correct GitHub account and whether I have been given access to the repository. I would also verify the repository URL and my authentication method. If everything is correct but access is still denied, I would ask the team lead or repository admin to grant the required permission.

# Your team normally uses Pull Requests, but you notice that another developer has pushed code directly to the main branch without review.
->I would first check whether the pushed code causes any issue. I would discuss it with the developer and team lead. To prevent this in the future, the team can enable branch protection rules on main, requiring Pull Requests and reviews before merging.

# You accidentally commit a large file, such as a build folder or a 500 MB log file, and try to push it to GitHub. The push is rejected because the file is too large.
->I would remove the large file from Git tracking, add it to .gitignore if it should never be committed, and create a new commit. If the large file is already part of the commit history, I would clean it from the Git history before pushing again.

# You worked on a feature for several days and made 15 small commits like fix, test, changes, etc. Before creating the Pull Request, your team asks you to keep the Git history clean.
->I would combine the related commits into fewer meaningful commits using interactive rebase (git rebase -i). I can squash the small commits, write proper commit messages, run tests, and then push the cleaned-up branch.

# Before creating a Pull Request, you want to check exactly what changes you made compared with the main branch.
->I would compare my feature branch with main using Git diff. I would review the changed files and lines, make sure there are no unwanted changes, run tests, and then create the Pull Request.






docker pull
docker images
docker run
docker ps
docker ps -a
docker stop
docker start
docker rm
docker rmi
docker run -d nginx
docker run -d --name mynginx nginx
docker run -d -p 8080:80 nginx
docker run -d --name mynginx -p 8080:80 nginx
docker logs <container>
docker logs -f mynginx->It keeps showing new log messages as they appear.
docker logs --tail 50 mynginx
docker exec ->is used to run a command inside an already running container.
docker exec -it myubuntu bash
-i → interactive
-t → terminal
docker build -t myapp ->Docker reads the Dockerfile and builds an image.
Tags->A tag is used to identify a particular version or variant of a Docker image.

docker compose up
docker compose up -d
docker compose down
docker compose ps
docker compose logs
docker compose logs backend ->For a specific service
services->Defines the containers/services that make up your application.
image->Specifies which Docker image should be used.
ports->
environment
volumes
docker push mahesh/myapp:1.0
docker compose version
docker compose up
docker compose up -d
docker compose down
docker compose ps
docker compose logs
docker compose logs -f
docker compose start
docker compose stop
docker compose restart
docker compose pause
docker compose unpause
docker compose build
docker compose pull
docker compose push
docker compose create
docker compose run
docker compose exec
docker compose kill
docker compose rm
docker compose config
docker compose images
docker compose top
docker compose events
docker compose port
docker compose cp
docker compose watch

# Docker Port Binding
  -So you need to connect your Windows/laptop port to the container port.
  ->docker run -p HOST_PORT:CONTAINER_PORT image
  -> docker run -p 8080:80 nginx
  - --name is used to give a custom name to a Docker container.
  -> docker run -d --name mynginx nginx


# Docker Logs
   -Show me what the application/container has printed
  -When an application runs inside a container, you often want to see what the application is printing.
  ->docker logs mynginx
  ->docker logs CONTAINER

  -It is similar to watching the logs continuously.
  ->docker logs -f mynginx
  ->ctl+c for stop


# docker exec
   -docker run Creates a new container
   -> Creates a new container:
   -docker exec Uses an existing running container:
   -> docker exec -it mynginx /bin/bash
   -To leave the container:
   ->exit


# Docker Volumes
   -Suppose MySQL is running inside a container:
   -If you delete the container:
   -the data stored inside that container's writable layer can be lost with the container.
   -So we need a place outside the container to store persistent data.
   -That's what a Docker volume is for.
   -Create a volume
   -> docker volume create mydata
   -Check:
   ->docker volume ls
   -Attach volume to a container
   -> docker run -d --name mymysql -v mydata:/data mysql
   -Inspect:
   -> docker volume inspect mydata
   -Delete:
   ->docker volume rm mydata
   ->docker run -d --name mysql2 -e MYSQL_ROOT_PASSWORD=root -v mydata:/var/lib/mysql -p 3306:3306 mysql:8


# Docker Network
   -Check your networks:
   -docker network ls
   -bridge
   --Let's create a network for our application:
   -->docker network create mynetwork
   -->docker network ls
   -- Run containers on the network
   --> docker run -d --name backend --network mynetwork my-spring-app



# Docker Compose
      -So Compose is especially useful for multi-container applications.
      -Docker Compose normally uses: compose.yaml,docker-compose.yml
      - Now run:
      -> docker compose up -d
      Check:
      ->docker compose ps
      -Stop everything:
      ->docker compose down
      -If you only want to stop the containers but not remove them:
      -> docker compose stop
      -Start the existing Compose application
      ->docker compose start

      -Now remove it:
      ->docker rm Name
      -Builds images for services that use:
      ->docker compose build

      -create database using compase 
      ->docker compose exec mysql mysql -u root -p
      -Build and start
      ->docker compose up -d --build
      --this is use-
            services
            image
            ports
            environment
            volumes
            depends_on
            healthcheck
            build
            container_name




Docker security means protecting containers, images, secrets, and the Docker host. Common practices include running containers as non-root users, using trusted and minimal images, keeping images updated, and avoiding secrets inside Dockerfiles.

Running a container as a non-root user reduces security risk because the application has fewer privileges. We can create a user in the Dockerfile and use the USER instruction to run the application as that user.

ARG is mainly used for values needed during image build time, while ENV is used for environment variables available when the container runs.

Docker networking allows containers to communicate with each other and with external systems. In a user-defined network, containers can communicate using service or container names because Docker provides DNS-based name resolution.

bridge->Bridge is the most commonly used network for containers on a single Docker host.
host ->With host networking, the container shares the host's network stack.
none ->none means the container gets no normal network connectivity.
overlay ->Overlay networking is designed for communication between containers/services running on different Docker hosts.

# Docker Networking Troubleshooting
            1)docker network ls ->Check available networks
            2)docker network inspect mynetwork ->Inspect a network
            3)docker inspect backend ->Check the container's network
            4)docker exec -it backend sh ->Test connectivity

For Docker networking troubleshooting, I first check the networks using docker network ls, inspect the network using docker network inspect, verify that the containers are on the same network, and test connectivity using the container or application port. I also check that I'm using the correct container or service name instead of localhost.

depends_on controls the startup order of Compose services, but it does not by itself guarantee that a dependency is ready. A healthcheck can verify that the dependency is healthy, and Compose can use condition: service_healthy to wait for it.

# Docker Troubleshooting — Container Keeps Restarting
->If a Docker container keeps restarting, I first check docker logs to find the application error. Then I check the container status with docker ps -a and inspect its configuration using docker inspect, including the command, environment variables, networking, and restart policy.

# Docker troubleshooting — container starts but application is not accessible
->If a Docker application is not accessible, I first check the port mapping with docker ps. Then I verify that the application is listening on the correct container port and preferably on 0.0.0.0. I also check the container logs and test the application from inside the container.

# Docker Image Vulnerability Scanning
-> 1) Docker Scout->Docker provides Docker Scout for analyzing images.
         exmple: docker scout cves myapp:1.0
         It can show known vulnerabilities such as:Critical,High,Medium,Low

Docker image vulnerability scanning checks an image for known security vulnerabilities in its base image, operating-system packages, and dependencies. Tools such as Docker Scout can be used to identify these vulnerabilities before deployment.

Docker uses layer caching to make image builds faster. If an earlier layer hasn't changed, Docker can reuse its cached result. We should place less frequently changing instructions, such as dependency installation, before frequently changing application code.

Docker Swarm is Docker's built-in container orchestration system. It allows multiple Docker hosts to work together as a cluster and manage services across them.



# What is Docker, and why do companies use it?
->Docker is a containerization platform that packages an application along with its dependencies into a container. Companies use Docker because it provides a consistent environment across development, testing, and production, and makes applications easier to deploy and manage.

# What is the difference between a Docker image and a Docker container?
->A Docker image is a read-only template that contains the application and its dependencies. A container is a running instance of that image.

# What is the difference between docker run and docker start?
->docker run creates a new container from an image and starts it. docker start starts an existing stopped container.

# What is the difference between docker stop and docker kill?
->docker stop gracefully stops a container by giving the application some time to shut down properly. docker kill immediately terminates the container without giving it that graceful shutdown time.

# What is the difference between docker rm and docker rmi?
->docker rm removes a container, while docker rmi removes a Docker image.

# What is port mapping in Docker, and why do we use -p?
->Port mapping connects a port on the host machine to a port inside the container. We use -p to allow users or other applications outside the container to access the application running inside it.

# What is a Dockerfile? Why do we use it?
->A Dockerfile is a text file that contains instructions for building a Docker image. We use it to define the application environment, dependencies, files, ports, and the command needed to start the application.

# What is the difference between CMD and ENTRYPOINT in Docker?
->CMD provides the default command or arguments for a container, and it can be easily overridden. ENTRYPOINT defines the main command that the container is intended to run.

# What is the difference between a Docker volume and a bind mount?
->A Docker volume is managed by Docker and is commonly used for persistent application or database data. A bind mount maps a specific folder or file from the host machine into the container and is commonly useful during development.

# What happens to the data when a Docker container is deleted?
->Data stored inside the container's writable layer is deleted when the container is removed. If we need the data to survive container deletion, we should use a Docker volume or bind mount.

# What is the difference between docker ps and docker ps -a?
->docker ps shows only the currently running containers. docker ps -a shows all containers, including running and stopped containers.

# What is a Docker network, and why do we use it?
->A Docker network allows containers to communicate with each other securely. When containers are on the same network, they can communicate using container or service names instead of hardcoded IP addresses.

# What is Docker Compose, and why do we use it?
->Docker Compose is a tool used to define and run multiple Docker containers as one application. We use it when our application has multiple services, such as a Spring Boot backend, MySQL database, Redis, and frontend.

# What is the difference between docker compose up and docker compose down?
->docker compose up creates and starts the services defined in the Compose file. docker compose down stops and removes the containers and the network created by Compose.

# What is the difference between EXPOSE in a Dockerfile and -p in docker run?
->EXPOSE documents which port the application inside the container is expected to listen on. It does not make the port accessible from the host by itself. -p actually publishes and maps the container port to a host port.

# What is Docker Hub?
->Docker Hub is a cloud-based registry where Docker images can be stored, shared, and downloaded. We can pull public images such as MySQL or Nginx from Docker Hub, and we can also push our own application images there.

# What is the difference between docker pull and docker build?
->docker pull downloads an already-built image from a Docker registry, while docker build creates a new Docker image using a Dockerfile and build context.

# What is the Docker image layer, and why is it useful?
->A Docker image is made up of multiple read-only layers. Each Dockerfile instruction can create a layer. Docker reuses unchanged layers from the cache, which makes future image builds faster and reduces build time.

# A Docker container is running, but your application is not accessible from the browser. How will you troubleshoot it?
->First, I will check whether the container is actually running using docker ps. Then I will check the container logs using docker logs. After that, I will verify the port mapping and confirm that the application is listening on the correct port inside the container. I will also check the Docker network and firewall if required.

# Your Spring Boot container is running, but it cannot connect to the MySQL container. How will you troubleshoot it?
->First, I will check whether both containers are running and are connected to the same Docker network. Then I will verify the database hostname, port, username, and password. If MySQL is running in another container, I will use the MySQL service name instead of localhost. Finally, I will check the Spring Boot and MySQL logs for connection errors.

# Your Docker container keeps restarting again and again. How will you find the problem?
->First, I will check the container status and restart count. Then I will check the container logs to find the application error. I will also inspect the container configuration, environment variables, ports, and health checks. If necessary, I will run the image interactively to investigate the issue.

# Your Docker image is very large and takes a long time to build and deploy. How would you reduce its size?
->I would use a smaller base image, use a multi-stage build, avoid unnecessary files, and create a proper .dockerignore file. For Java applications, I can build the application in one stage and copy only the final JAR into a smaller runtime image.

# What is a multi-stage Docker build, and why do we use it?
->A multi-stage build uses multiple stages in a Dockerfile. We can use one stage to build the application and another smaller stage to run it. This keeps build tools and unnecessary files out of the final image, making the image smaller and more secure.

# What is a .dockerignore file, and why do we use it?
->.dockerignore is a file that tells Docker which files and directories should not be included in the build context when building an image. It helps reduce build time, image size, and prevents unnecessary or sensitive files from being copied.

# Your Docker build is taking a long time every time, even though you changed only one source file. How would you improve the build time?
->I would check the Dockerfile layer order and Docker build cache. I would place instructions that change less frequently, such as installing dependencies, before instructions that change frequently, such as copying source code. This allows Docker to reuse cached layers.

# Your Docker container is using too much CPU. How will you investigate and troubleshoot it?
->First, I will check the container's CPU usage using Docker statistics. Then I will check the application logs and identify which process or operation is consuming high CPU. I will also check whether there is an application issue, such as an infinite loop, excessive requests, or inefficient processing.

# Your Docker container is using too much memory and may be causing an Out Of Memory issue. How will you troubleshoot it?
->First, I will check the container's memory usage using docker stats. Then I will check the application logs and container configuration. For a Java application, I would also investigate JVM heap usage and garbage collection to determine whether the problem is with the application or the container's memory limit.

# What happens if two Docker containers try to use the same host port?
->Docker cannot bind the same host port to two containers at the same time. The second container will fail to start because that host port is already in use.

# What is the difference between a container's internal port and the host port?
->The container port is the port on which the application listens inside the container. The host port is the port exposed on the host machine so users can access the application from outside the container.

# A container exits immediately after you start it. What could be the reason?
->I would first check the container status and logs to find why the main process exited. Then I would verify the Dockerfile, environment variables, and application configuration and fix the root cause.

# What is a Docker restart policy? Why do we use it?
->A Docker restart policy tells Docker when to automatically restart a container. It is useful for applications that should recover automatically if the container stops unexpectedly.

# What is the difference between docker logs and docker inspect?
->docker logs shows the output and error logs generated by a container, while docker inspect shows detailed information about the container's configuration and runtime state.

# Your Spring Boot application works on your laptop but fails when running inside Docker. What would you check?
->First, I would check the Docker container logs to identify the error. Then I would verify the environment variables, application configuration, Java version, database connection, network settings, and required files inside the image. I would also make sure the application is listening on the correct port.


# What is a Docker registry, and what is the difference between a registry and Docker Hub?
->A Docker registry is a storage system used to store and distribute Docker images. Docker Hub is a public Docker registry service provided by Docker.

# What is the difference between docker push and docker pull?
->docker push uploads a Docker image from your local machine to a Docker registry. docker pull downloads an image from a registry to your local machine or server.

# You pushed a new Docker image with the same tag, such as latest, but your server is still running the old version. What would you check?
->First, I would check which image the running container was created from. Then I would pull the latest image on the server and recreate the container. Simply pushing a new image does not automatically update an already-running container.

# Why should we avoid using the latest tag in production?
->The latest tag is not a fixed version. It can point to a different image when a new image is pushed, which can make deployments unpredictable. In production, I prefer specific version tags so I know exactly which image is deployed.

# Your application is working inside the Docker container, but it cannot connect to an external API such as a payment or authentication service. How would you troubleshoot it?
->First, I would check the container logs and verify the API URL and environment variables. Then I would test network connectivity from inside the container. I would also check DNS resolution, proxy or firewall settings, TLS/SSL errors, and whether the external API is reachable from the server.

# Your Docker container can connect to the internet using an IP address, but it cannot connect using a domain name. What could be the problem?
->This usually indicates a DNS resolution problem inside the container. I would check the container's DNS configuration and verify whether the Docker host and Docker network can resolve the domain.

# A Docker container is running, but its health check shows unhealthy. What does this mean, and how would you troubleshoot it?
->Unhealthy means the container is running, but its health check is failing. I would check docker logs, inspect the health-check result with docker inspect, and test the application from inside the container to find the problem.

# Your Docker container is running, but after restarting the container, all application data is lost. How would you prevent this?
->I would use a Docker volume or bind mount for data that needs to persist. The application should not depend on the container's writable filesystem for important data.

# In production, your Docker container suddenly stops. How would you handle the situation?
->First, I would check whether the container stopped because of an application error, resource issue, or infrastructure problem. I would check the container status and logs, then investigate CPU and memory usage. If the application is safe to restart, I would restart or redeploy it while continuing to investigate the root cause.

# Your Docker container is running, but the application inside it is very slow. How would you troubleshoot it?
->First, I would check CPU and memory usage using docker stats. Then I would check application logs and identify whether the problem is caused by the application, database, network, or limited container resources. For a Spring Boot application, I would also check JVM memory and garbage collection if necessary.

# What is a Docker container restart loop, and what are the common reasons for it?
->A restart loop happens when a container starts, crashes, and Docker repeatedly starts it again. It usually means the main application process is failing during startup.

# How would you securely pass passwords and secrets to a Docker container?
->I would avoid hardcoding passwords or API keys inside the Dockerfile or source code. For local development, I can use environment variables or a .env file that is not committed to Git. In production, I would prefer a proper secrets-management solution.

# How do you check how much disk space Docker is using?
->I use docker system df to check the disk space used by Docker images, containers, local volumes, and build cache.

# What is docker system prune, and what should you be careful about when using it?
->docker system prune removes unused Docker resources, such as stopped containers, unused networks, dangling images, and build cache. It helps free disk space.

# You have deployed a new Docker version of your Spring Boot application, but the new version has a critical bug. How would you roll back to the previous version?
->I would deploy the previously tested Docker image version instead of latest. If the previous image is still available in the registry, I would pull that specific version and recreate the container. Then I would verify that the application is healthy.

# What is the difference between a Docker container and a virtual machine (VM)?
->A Docker container shares the host operating system's kernel, while a virtual machine has its own complete guest operating system. Because containers share the kernel, they are generally lighter and start faster than VMs.

# How would you deploy a Spring Boot application using Docker in a real project?
->First, I would build the Spring Boot application and generate the JAR file. Then I would create a Dockerfile to build the application image. After that, I would build and tag the image, run it locally for testing, and push the image to a Docker registry. Finally, on the server, I would pull the required image version and run or deploy the container. If the application has multiple services, I would use Docker Compose or another orchestration platform.

# In a production environment, your Docker container is running but suddenly becomes unhealthy. What would you check first?
->First, I would check the container's health status and health-check output. Then I would check application logs, CPU and memory usage, database connectivity, and whether the application endpoint used by the health check is responding correctly.




