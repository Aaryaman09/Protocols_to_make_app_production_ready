# Protocols to make app production ready:

## Here are the protocols and steps required to follow to make a simple Flask application production and deployment ready:

1. Set up a virtual environment: Create a virtual environment using a tool like venv or conda to ensure that your application has its own isolated environment with all the dependencies it needs.

2. Install Flask: Install Flask using pip, the Python package installer. You can do this in your virtual environment by running pip install flask.

3. Configure your application: Create a configuration file for your application. This file should contain settings for your application, such as the database URL, secret key, and other environment variables. You can use python-dotenv to load environment variables from a .env file.

4. Write your application code: Write the Flask application code in a Python file, typically named app.py. This file should define routes for your application, which correspond to URLs that users can visit to interact with your application.

5. Test your application: Test your application to ensure that it works as expected. You can use a tool like pytest to write and run tests for your application.

6. Containerize your application: Use a tool like Docker to containerize your application. This involves creating a Dockerfile that defines the environment and dependencies for your application, as well as any necessary commands for running the application.

7. Push your container to a container registry: Push your container to a container registry, such as Docker Hub or Amazon ECR. This makes it easy to deploy your application to a production environment.

8. Deploy your application: Deploy your container to a production environment, such as a cloud provider like AWS or Google Cloud Platform. You can use a tool like Kubernetes or Docker Swarm to manage and orchestrate your containers.

9. Monitor your application: Use a monitoring tool like Prometheus or Grafana to monitor your application's performance and health. This can help you identify and fix issues before they become major problems.

10. Continuously deploy new versions: Set up a continuous deployment pipeline to automatically deploy new versions of your application when changes are pushed to the code repository. This can help you quickly and easily deploy updates and bug fixes to your application.

These are the basic protocols and steps required to make a simple Flask application production and deployment ready. Of course, there may be additional steps and considerations depending on the specific requirements of your application and your deployment environment.

## Here are some additional steps you may need to consider when making a Flask application production and deployment ready:

1. Use a WSGI server: While Flask has a built-in development server, it's not recommended for production use. Instead, you should use a production-ready WSGI (Web Server Gateway Interface) server like Gunicorn, uWSGI or mod_wsgi to serve your Flask application.

2. Set up logging: Proper logging is crucial for monitoring and debugging your application in production. Configure your application to log important events and errors to a file or to a centralized logging system.

3. Enable HTTPS: Enabling HTTPS (HTTP Secure) is important to ensure that data sent between your application and its users is encrypted and secure. You can obtain SSL/TLS certificates from a certificate authority like Let's Encrypt, and use a web server like Nginx or Apache to serve your application over HTTPS.

4. Set up load balancing and scaling: If your application receives a high volume of traffic, you may need to set up load balancing and scaling to ensure that it can handle the load. You can use a load balancer like HAProxy or an auto-scaling service like AWS Elastic Beanstalk to automatically adjust the number of instances of your application based on demand.

5. Secure your application: Securing your application is critical to prevent unauthorized access, data breaches, and other security risks. You can implement security measures like user authentication and authorization, input validation, and session management to protect your application.

6. Set up backups and disaster recovery: It's important to have a plan for backing up and restoring your application data in case of data loss or other disasters. You can use tools like AWS Backup or Google Cloud Storage to automatically back up your data, and implement a disaster recovery plan to restore your application in case of a failure.

These are just a few additional steps to consider when making a Flask application production and deployment ready. The specific steps you need to take will depend on your application's requirements, your deployment environment, and your organization's policies and best practices.

## Here are the necessary steps and protocols to take to make your app production and deployment ready:

1. Create a production-ready build: Ensure that your application code is thoroughly tested, optimized, and secure. You should also remove any debug code and set up environment-specific configurations.

2. Set up a version control system: Use a version control system like Git to manage your codebase and track changes.

3. Use a continuous integration and delivery (CI/CD) pipeline: A CI/CD pipeline automates the build, test, and deployment process. Use a pipeline to build, test, and deploy your application to a staging environment.

4. Set up a staging environment: A staging environment is a replica of the production environment that is used to test changes before they are deployed to production. Ensure that the staging environment is configured to match the production environment as closely as possible.

5. Monitor your application: Use monitoring tools to track application performance, errors, and other metrics. Ensure that your monitoring tools are set up to alert you if any critical issues arise.

6. Use load testing tools: Load testing tools help you simulate high traffic and test how your application performs under load. Use load testing tools to ensure that your application can handle the expected traffic.

7. Ensure security: Security is critical in production environments. Ensure that your application is secured by using HTTPS, setting up firewalls, and using authentication and authorization.

8. Automate infrastructure provisioning: Use infrastructure as code tools like Terraform or CloudFormation to automate the provisioning and management of your infrastructure.

9. Use containerization: Containerization allows you to package your application and its dependencies into a single unit. Use containerization tools like Docker to make your application portable and easier to manage.

10. Set up a disaster recovery plan: A disaster recovery plan outlines the steps to be taken in case of an outage or failure. Ensure that your disaster recovery plan is regularly tested and updated.

By following these steps and protocols, you can ensure that your application is production and deployment ready.

## Here's an example of creating a simple Flask application that is production-ready:

1. Create a virtual environment: It's best practice to create a virtual environment to isolate your dependencies from your system's Python installation. You can create a virtual environment by running the following command:

```javascript
python3 -m venv myvenv
```

2. Activate the virtual environment: Activate the virtual environment by running the following command:

```bash
source myvenv/bin/activate
```

3. Install Flask: Install Flask using pip:

```
pip install flask
```

4. Create your Flask app: Create a file called **app.py** with the following code:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run()
```

5. Set up environment variables: Set up environment variables to store sensitive information like passwords and API keys. You can use the **python-dotenv** library to load environment variables from a **.env** file. Install the library by running:

```
pip install python-dotenv
```

Then create a **.env** file with the following content:

```makefile
SECRET_KEY=your_secret_key_here
DATABASE_URL=your_database_url_here
```

In your **app.py** file, you can load environment variables by adding the following code:

```python
import os
from dotenv import load_dotenv

load_dotenv()

app.secret_key = os.getenv('SECRET_KEY')
app.config['SQLALCHEMY_DATABASE_URI'] = os.getenv('DATABASE_URL')
```

6. Use HTTPS: It's essential to use HTTPS to secure your application. You can use the **flask-sslify** library to redirect HTTP requests to HTTPS. Install the library by running:

```
pip install flask-sslify
```

Then add the following code to your **app.py** file:

```python
from flask_sslify import SSLify

sslify = SSLify(app)
```

7. Use Gunicorn: Gunicorn is a production-ready web server that can handle multiple requests concurrently. Install Gunicorn by running:

```
pip install gunicorn
```

Then start your Flask app using Gunicorn by running:

```
gunicorn app:app
```

With these steps, you can create a production-ready Flask application.

## Here's how you can use Git to manage your Flask application codebase:

1. Initialize a Git repository: In your project directory, run the following command to initialize a Git repository:
```csharp
git init
```
2. Create a **.gitignore** file: Create a **.gitignore** file to ignore files and directories that shouldn't be tracked by Git. Here's an example **.gitignore** file for a Flask application:

```bash
# Ignore compiled Python files
*.pyc

# Ignore the virtual environment
myvenv/

# Ignore environment variables file
.env
```

3. Stage and commit your code: Stage your changes by running the following command:
```sql
git add .

# or if you want to add only specific files
git add app.py requirements.txt
```

Then commit your changes by running:

```sql
git commit -m "Initial commit"
```

4. Create a remote repository: Create a remote repository on a Git hosting service like GitHub, GitLab, or Bitbucket.

5. Add the remote repository: Add the remote repository as a Git remote by running the following command:

```csharp
git remote add origin <remote_repository_url>
```

6. Push your code to the remote repository: Push your changes to the remote repository by running the following command:
```perl
git push -u origin master
```

Now your Flask application code is managed by Git and stored on a remote repository. You can track changes, collaborate with others, and deploy your code using Git.

## Here's how you can use a requirements.txt file to manage your Flask application's dependencies:

1. Install pip-tools: Install the **pip-tools** package by running the following command:

```
pip install pip-tools
```

2. Create a requirements.in file: Create a file called **requirements.in** in your project directory and add the following line to it:

```
flask
```

You can add other dependencies that your Flask app needs.

Generate a requirements.txt file: Generate a **requirements.txt** file from the **requirements.in** file by running the following command:

```python
pip-compile requirements.in
```

This command generates a **requirements.txt** file that includes the dependencies specified in **requirements.in** and their dependencies.

4. Install the dependencies: Install the dependencies listed in the **requirements.txt** file by running the following command:

```
pip install -r requirements.txt
```

This command installs the dependencies required for your Flask app to run.

Now you have a **requirements.txt** file that lists all the dependencies for your Flask app. You can use this file to install the dependencies on your production server, making sure that all the dependencies are available in the production environment.

## Point 4: Here are some steps to configure logging for your Flask application:

1. Import the logging module: In your **app.py** file, import the **logging** module:
```python
import logging
```

2. Configure the logger: Configure the logger by adding the following code to your **app.py** file:

```python
logging.basicConfig(level=logging.DEBUG,
                    format='%(asctime)s [%(levelname)s] %(message)s',
                    handlers=[
                        logging.StreamHandler(),
                        logging.FileHandler('app.log')
                    ])
```

This code configures the logger to write logs to the console and a file called app.log. The log messages will include the timestamp, log level, and message.

3. Use the logger: Use the logger to log messages in your Flask app by adding the following code to your **app.py** file:
```python
app.logger.info('This is an info message')
app.logger.warning('This is a warning message')
app.logger.error('This is an error message')
```

You can replace the log levels and messages with your own messages.

4. Test the logging: Start your Flask app and check the logs in the console and the app.log file to make sure that the logger is working correctly.

By configuring the logger in your Flask app, you can capture useful information about your app's behavior and troubleshoot issues that may arise in production. You can also configure log rotation to manage log files and prevent them from consuming too much disk space.

## Here's an example Dockerfile for the Flask app we created earlier:

```Dockerfile
# Use an official Python runtime as a parent image
FROM python:3.9-slim-buster

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Set the environment variable for Flask
ENV FLASK_APP=app.py

# Expose port 5000 for Flask app
EXPOSE 5000

# Run the command to start the Flask app
CMD ["flask", "run", "--host=0.0.0.0"]
```

Let's go through each of the steps:

1. **FROM python:3.9-slim-buster**: Use the official Python 3.9 slim-buster image as the base image.

2. **WORKDIR /app**: Set the working directory to **/app**.

3. **COPY . /app**: Copy the current directory (which includes **app.py**, **requirements.txt**, and any other files needed for the app) into the container at **/app**.

4. **RUN pip install --no-cache-dir -r requirements.txt**: Install the dependencies specified in **requirements.txt**. We use **--no-cache-dir** to avoid caching the packages and making the image smaller.

5. **ENV FLASK_APP=app.py**: Set the environment variable **FLASK_APP** to **app.py**, which is the name of our Flask app.

6. **EXPOSE 5000**: Expose port 5000, which is the port used by the Flask app.

7. **CMD ["flask", "run", "--host=0.0.0.0"]**: Start the Flask app by running the command **flask run** and passing the **--host=0.0.0.0** flag to allow connections from outside the container.

To build the Docker image, navigate to the directory containing the Dockerfile and run the following command:

```
docker build -t myflaskapp .
```
This will build the Docker image with the tag **myflaskapp**. You can then run the Docker container using the following command:

```
docker run -p 5000:5000 myflaskapp
```

This will start the container and forward port 5000 to your local machine, allowing you to access the Flask app in your web browser at **http://localhost:5000**.

## Here's an updated Dockerfile that uses Gunicorn to run the Flask app:

```Dockerfile
# Use an official Python runtime as a parent image
FROM python:3.9-slim-buster

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Set the environment variable for Gunicorn
ENV PORT=5000

# Expose port 5000 for Gunicorn
EXPOSE 5000

# Run the command to start the Flask app using Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:$PORT", "app:app"]
```

The changes are as follows:

1. Removed the **ENV FLASK_APP=app.py** line, since it's not needed when using Gunicorn.

2. Added an **ENV PORT=5000** line to set the port number.

3. Changed the **CMD** line to run Gunicorn instead of Flask. The command **gunicorn --bind 0.0.0.0:$PORT app:app** starts Gunicorn and binds it to port 5000, using the **app:app** argument to tell Gunicorn where to find the Flask app.

To build the Docker image, navigate to the directory containing the Dockerfile and run the following command:

```
docker build -t myflaskapp .
```

This will build the Docker image with the tag myflaskapp. You can then run the Docker container using the following command:

```
docker run -p 5000:5000 myflaskapp
```

This will start the container and forward port 5000 to your local machine, allowing you to access the Flask app in your web browser at http://localhost:5000.

## To expose the application on a dynamically assigned port, you can modify the **CMD** line in the Dockerfile to use the **PORT** environment variable that's set at runtime.

Here's the updated **Dockerfile**:

```Dockerfile
# Use an official Python runtime as a parent image
FROM python:3.9-slim-buster

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Set the environment variable for Gunicorn
ENV PORT=5000

# Expose the port that will be used by the Flask app
EXPOSE $PORT

# Run the command to start the Flask app using Gunicorn
CMD ["sh", "-c", "gunicorn --bind 0.0.0.0:$PORT app:app"]
```

The changes are as follows:

1. The **ENV PORT=5000** line sets the default port to 5000, but it can be overridden at runtime.

2. The **EXPOSE** line now uses the $PORT variable to dynamically expose the port that will be used by the Flask app.

3. The **CMD** line has been modified to run a shell script that sets the PORT environment variable and starts the Flask app using Gunicorn.

To build the Docker image, navigate to the directory containing the Dockerfile and run the following command:

```
docker build -t myflaskapp .
```

This will build the Docker image with the tag **myflaskapp**. You can then run the Docker container using the following command:

```
docker run -p <external_port>:<internal_port> -e PORT=<internal_port> myflaskapp
```

Replace **<external_port>** with the port number you want to use to access the Flask app from your local machine, and **<internal_port>** with the port number you want to use for the Flask app inside the Docker container (which should match the value of the **PORT** environment variable).

For example, if you want to expose the app on port **8000** on your local machine and use port 5000 inside the container, you would run:

```python
docker run -p 8000:5000 -e PORT=5000 myflaskapp
```

This will start the container and forward port 8000 to your local machine, allowing you to access the Flask app in your web browser at http://localhost:8000.

The **sh** and **-c** options in the **CMD** instruction are used to execute a shell command inside the Docker container.

The **sh** option specifies the shell program to use for executing the command. In this case, it's the default shell program, which is usually Bash or another compatible shell.

The **-c** option specifies that the following argument is a shell command to execute. In our Dockerfile, we're using the **CMD** instruction to specify the Gunicorn command to run the Flask app. By using the **-c** option, we're telling Docker to execute this command in a shell inside the container.

So the CMD instruction in our Dockerfile essentially translates to the following shell command:

```python
sh -c 'gunicorn --bind 0.0.0.0:$PORT app:app'
```

This command uses the shell program (sh) to execute the Gunicorn command with the specified options and arguments. The **$PORT** environment variable is expanded to its actual value at runtime, thanks to the use of the $ symbol in front of the variable name.

## Here's a detailed explanation of each line in the Dockerfile:

```
FROM python:3.9-slim-buster
```

This line specifies the base image to use for the Docker container. In this case, we're using the official Python 3.9 slim image, which is a lightweight version of the Python runtime environment based on the Debian Buster operating system.

```bash
WORKDIR /app
```

This line sets the working directory inside the Docker container to /app. This is where we'll copy the Flask app code and any other files needed by the app.

```bash
COPY . /app
```

This line copies the current directory (i.e., the directory containing the Dockerfile) into the Docker container at the /app directory. This will include the Flask app code and any other files needed by the app, such as the requirements.txt file.

```python
RUN pip install --no-cache-dir -r requirements.txt
```

This line runs the pip install command inside the Docker container to install the dependencies listed in the requirements.txt file. The --no-cache-dir option tells pip not to use the cache, which helps keep the Docker image size smaller.

```
ENV PORT=5000
```

This line sets the default value of the PORT environment variable to 5000. This variable will be used to specify the port number that the Flask app listens on.

```bash
EXPOSE 5000
```

This line specifies that the Docker container should listen on port 5000. Note that this doesn't actually publish the port to the host machine -- we'll do that later when we run the container.

```bash
CMD ["gunicorn", "--bind", "0.0.0.0:$PORT", "app:app"]
```

This line specifies the command to run when the Docker container starts. In this case, we're using Gunicorn to run the Flask app, and we're passing in the **--bind** option to tell Gunicorn to bind to the IP address **0.0.0.0** (which means it will listen on all network interfaces) and the **$PORT** environment variable (which will be replaced with the actual port number at runtime). The **app:app** argument tells Gunicorn where to find the Flask app -- in this case, it's located in the **app.py** file and the **app** variable inside that file is the Flask app instance.

> Q : what is ENV PORT=5000 and EXPOSE $PORT in our docker file and how are they different?

A : ENV PORT=5000 and EXPOSE $PORT are both instructions in our Dockerfile that relate to the port number that the Flask app will listen on. However, they serve slightly different purposes.

ENV PORT=5000 sets the default value of the PORT environment variable to 5000. This variable will be used to specify the port number that the Flask app listens on. By default, the Flask app will listen on port 5000 unless a different port number is specified at runtime.

EXPOSE $PORT is used to indicate to Docker that the container will listen on the port number specified in the PORT environment variable. In our Dockerfile, we've set PORT to 5000, so EXPOSE $PORT is equivalent to EXPOSE 5000. This instruction doesn't actually publish the port to the host machine -- it's just a way of documenting which port the container is listening on.

When we run the container, we can map the container's port to a port on the host machine using the -p option. For example, if we want to map the container's port 5000 to the host machine's port 8000, we can run the following command:

```
docker run -p 8000:5000 my-flask-app
```

This command tells Docker to start a container based on the my-flask-app image and map the container's port 5000 to the host machine's port 8000. Now, we can access the Flask app by visiting http://localhost:8000 in our web browser.

> Q : in our docker file, why -e is used in docker run command?

A : The -e option in the docker run command is used to set environment variables inside the Docker container. In our case, we're using the -e option to set the value of the PORT environment variable to a dynamic port number that is passed as a command-line argument when we run the container.

Here's the full docker run command we're using:

```
docker run -p $HOST_PORT:$PORT -e PORT=$PORT my-flask-app
```

Let's break down what each part of the command does:

-p $HOST_PORT:$PORT maps the container's port (specified by the PORT environment variable) to a port on the host machine (specified by the $HOST_PORT command-line argument).
-e PORT=$PORT sets the value of the PORT environment variable inside the container to the value of the $PORT command-line argument.
my-flask-app is the name of the Docker image that we want to run.
By using the -e option to set the value of the PORT environment variable, we're making it possible to run the Flask app on a dynamic port number that can be specified at runtime. This is useful when deploying the app to a cloud platform like Heroku or Kubernetes, where the port number may not be known in advance.

> Q : so -e PORT=$PORT port value is sent to $PORT in -p ?
    
A : In the docker run command, the -e PORT=$PORT option sets the value of the PORT environment variable inside the container to the value of the $PORT command-line argument. This means that the Flask app will listen on the port number specified by the $PORT argument.

The -p $HOST_PORT:$PORT option maps the container's port (specified by the PORT environment variable) to a port on the host machine (specified by the $HOST_PORT command-line argument). The $HOST_PORT argument is a variable that we're passing in at runtime, and it specifies the port number on the host machine that we want to use to access the Flask app.

So to answer your question: the value of $PORT is used in both the -e and -p options, but for different purposes. In the -e option, it sets the value of the PORT environment variable inside the container, while in the -p option, it specifies the port number that the Flask app will listen on inside the container. The value of $HOST_PORT, on the other hand, is used only in the -p option to specify the port number on the host machine that we want to use to access the Flask app.

## Here's an example YAML file for a CircleCI pipeline that builds the Docker image, pushes it to Docker Hub, and deploys it to Heroku:

```yaml
version: 2.1

orbs:
  heroku: circleci/heroku@1.0.5

jobs:
  build:
    docker:
      - image: circleci/python:3.9-buster
    steps:
      - checkout
      - run: docker build -t your-dockerhub-username/flask-app:latest .
      - run: docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD
      - run: docker push your-dockerhub-username/flask-app:latest
  deploy:
    docker:
      - image: circleci/python:3.9-buster
    steps:
      - checkout
      - heroku/install
      - run:
          name: Deploy to Heroku
          command: heroku container:release web -a your-heroku-app-name
    requires:
      - build

workflows:
  build-and-deploy:
    jobs:
      - build
      - deploy:
          requires:
            - build
          filters:
            branches:
              only: main
```

Here's a brief explanation of each section of the YAML file:

1. version: This specifies the version of the CircleCI pipeline syntax to use.

2. orbs: This defines a reusable set of configuration elements, or "orbs", that can be included in multiple pipelines. In this case, we're using the heroku orb to simplify the deployment to Heroku.

3. jobs: This defines one or more named jobs that can be run as part of the pipeline. In this case, we have two jobs: build and deploy.

4. build: This job builds the Docker image, pushes it to Docker Hub, and stores it for use in the deploy job. It uses the official circleci/python Docker image as the build environment, checks out the code from the repository, builds the Docker image with docker build, logs in to Docker Hub with the $DOCKERHUB_USERNAME and $DOCKERHUB_PASSWORD environment variables, and pushes the image to Docker Hub.

5. deploy: This job deploys the Docker image to Heroku. It also uses the circleci/python Docker image as the build environment, checks out the code from the repository, installs the Heroku CLI with the heroku/install step, and deploys the Docker image to Heroku with the heroku container:release command.

6. requires: This specifies that the deploy job depends on the build job, meaning that the build job must complete successfully before the deploy job can run.

7. filters: This specifies that the deploy job should only run on the main branch.

8. workflows: This defines one or more named workflows that specify the jobs to run and the order in which to run them. In this case, we have a single workflow called build-and-deploy that runs the build job followed by the deploy job, but only on the main branch.

## Here's a more detailed explanation of each section of the YAML file:

```makefile
version: 2.1
```

This line specifies the version of the CircleCI pipeline syntax to use. In this case, we're using version 2.1.

```yaml
orbs:
  heroku: circleci/heroku@1.0.5
```

This section defines a reusable set of configuration elements, or "orbs", that can be included in multiple pipelines. In this case, we're using the heroku orb to simplify the deployment to Heroku. The circleci/heroku@1.0.5 refers to the version of the heroku orb to use.

```yaml
jobs:
  build:
    docker:
      - image: circleci/python:3.9-buster
    steps:
      - checkout
      - run: docker build -t your-dockerhub-username/flask-app:latest .
      - run: docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD
      - run: docker push your-dockerhub-username/flask-app:latest
```

This section defines one named job, build, that builds the Docker image and pushes it to Docker Hub.

The docker section specifies the Docker image to use as the build environment. In this case, we're using the official circleci/python Docker image with Python version 3.9 and the Debian Buster operating system.

The steps section defines the individual steps to run in the job.

The checkout step checks out the code from the repository.

The docker build step builds the Docker image with the name your-dockerhub-username/flask-app:latest.

The docker login step logs in to Docker Hub using the $DOCKERHUB_USERNAME and $DOCKERHUB_PASSWORD environment variables.

The docker push step pushes the Docker image to Docker Hub with the name your-dockerhub-username/flask-app:latest.

```yaml
  deploy:
    docker:
      - image: circleci/python:3.9-buster
    steps:
      - checkout
      - heroku/install
      - run:
          name: Deploy to Heroku
          command: heroku container:release web -a your-heroku-app-name
    requires:
      - build
```

This section defines one named job, deploy, that deploys the Docker image to Heroku.

The docker section specifies the Docker image to use as the build environment. In this case, we're using the same official circleci/python Docker image as in the build job.

The steps section defines the individual steps to run in the job.

The checkout step checks out the code from the repository.

The heroku/install step installs the Heroku CLI.

The run step runs the heroku container:release command to deploy the Docker image to the Heroku app with the name your-heroku-app-name.

The requires section specifies that the deploy job depends on the build job, meaning that the build job must complete successfully before the deploy job can run.

```yaml
workflows:
  build-and-deploy:
    jobs:
      - build
      - deploy:
          requires:
            - build
          filters:
            branches:
              only: main
```

The workflows section defines a single workflow with the name build-and-deploy. This workflow consists of two jobs, build and deploy, which will run in the order specified.

The build job is defined earlier in the YAML file and builds the Docker image.

The deploy job is also defined earlier in the YAML file and deploys the Docker image to Heroku.

The requires keyword under deploy specifies that the deploy job depends on the build job, meaning that the build job must complete successfully before the deploy job can run.

The filters keyword under deploy specifies the conditions that must be met for the deploy job to run. In this case, the deploy job will only run if changes are made to the main branch of the repository.

Overall, the workflows section enables us to define the order and conditions for running multiple jobs, which allows us to automate the build and deployment process with CircleCI.

