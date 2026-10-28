git clone https://github.com/YOUR-USERNAME/git-demo.git
cd git-demo

echo "Hello GitHub" > file1.txt

git add file1.txt
git commit -m "Initial commit"
git push origin main

git branch feature1
git checkout feature1

echo "Feature branch update" >> file1.txt
git add file1.txt
git commit -m "Feature branch update"
git push origin feature1

git diff main feature1

git checkout main
echo "Main branch change" >> file1.txt
git add file1.txt
git commit -m "Main branch change"

git merge feature1

git add file1.txt
git commit -m "Merge conflict resolved"
git push origin main

git checkout feature1
git push origin feature1



22222222222222222

docker --version

docker pull tomcat:10.1-jdk17-temurin

mkdir myapp3
cd myapp3

echo "<html><body><h1>Welcome to MyApp3</h1></body></html>" > index.html

echo FROM tomcat:10.1-jdk17-temurin > Dockerfile
echo COPY index.html /usr/local/tomcat/webapps/myapp3/index.html >> Dockerfile
echo EXPOSE 8080 >> Dockerfile

docker build -t aishwarya-myapp .
docker images

docker run -d --name myapp3-container -p 8081:8080 aishwarya-myapp

docker ps

docker logs myapp3-container

docker stop myapp3-container


333333333333333333333333333333



tomcat

→ create new folder with name "myapp" & create "index.html" file.

→ Create Dockerfile inside myapp & type this

FROM tomcat:10.1-jdk17-temurin
COPY index.html /usr/local/tomcat/webapps/myapp/index.html
EXPOSE 8080

→ Go to cmd inside myapp folder, type this

docker build -t my-tomcat .
docker images
docker run -d -p 8081:8080 --name my-tomcat-container my-tomcat

→ open chrome, localhost:8081/myapp/

it should display what you hv written in html.


4444444444444444444444444444

1. Create a GitHub repository.
2. Create a file in the repository.

   File: Readme.md

   Content: Welcome to my github.
3. In cmd type the command:

   cloudflared-windows-amd64.exe tunnel --url http://localhost:8080
   
4. Create a new item in Jenkins >  freestyleProject

5. Source Code Management > Git > Paste GitHub repo URL > Cross check the branch name in GitHub.

6. Triggers > GitHub hook triggers for GITScm Polling.

7. Build Steps > Add build steps > Execute Windows batch command > Apply > Save.

8. Copy the link from cmd from the box and paste it to Webhooks.

   After pasting the link type /github-webhook/

9. Content type > application/json > Add webhook.

10. Verify the webhook.
11. Edit the readme file, add extra line and commit changes.
12. Go to Jenkins, automatic build will create.



555555555555555555555555555555555555555555

.github(folder)(workflow)

name: Java CI/CD Pipeline

on:
  push:
    branches: ["main"]
  pull_request:
    branches: ["main"]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up JDK 21
        uses: actions/setup-java@v4
        with:
          java-version: '21'
          distribution: 'temurin'

      - name: Compile Java program
        run: javac new.java

      - name: Run Java program
        run: java New

new.jave (this file paste)
        
class New {
    public static void main(String[] args) {
        System.out.println("Hello Aishwarya!");
        System.out.println("Maven CI/CD Pipeline");
    }
}

44444444444444444444444

# PROGRAM 10: DOCKER AND JENKINS PIPELINE

## Step 1: Open Docker Desktop and verify installation

```cmd
docker version
docker images
```

## Step 2: Create a folder named Program10 on Desktop

```cmd
cd %USERPROFILE%\Desktop
mkdir Program10
cd Program10
notepad app.py
```

`app.py` file alli:

```python
print("Hello Aishwarya!")
print("Docker Image Build")
```

Save maadi close maadu.

## Step 3: Create Dockerfile

```cmd
notepad Dockerfile
```

Dockerfile alli ee code paste maadu:

```dockerfile
FROM python:3.10
WORKDIR /app
COPY app.py .
CMD ["python", "app.py"]
```

Save maadi close maadu.

## Step 4: Build and run Docker image

```cmd
docker build -t program10 .
docker images
docker run --rm program10
```

## Step 5: Tag and push Docker image to Docker Hub

```cmd
docker login
docker tag program10 aishwarya0625/program10:latest
docker push aishwarya0625/program10:latest
```

## Step 6: Push project code to GitHub

```cmd
git init
git add .
git commit -m "Program 10 Docker Project"
git branch -M main
git remote add origin https://github.com/Aishwarya0625/Program10.git
git push -u origin main
```

## Step 7: Create Docker Hub access token

1. Open https://hub.docker.com/
2. Login to Docker Hub.
3. Go to Account Settings.
4. Open Personal access tokens.
5. Click Generate new token.
6. Give token name `jenkins-token`.
7. Select required read/write permissions and generate token.
8. Copy and save the token securely.

## Step 8: Create Jenkinsfile

```cmd
notepad Jenkinsfile
```

Paste this code:

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Aishwarya0625/Program10.git'
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t aishwarya0625/program10:latest .'
            }
        }

        stage('Login') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-token', variable: 'TOKEN')]) {
                    bat 'echo %TOKEN% | docker login -u aishwarya0625 --password-stdin'
                }
            }
        }

        stage('Push') {
            steps {
                bat 'docker push aishwarya0625/program10:latest'
            }
        }
    }
}
```

Save maadi close maadu. GitHub-ge Jenkinsfile kooda push maadu:

```cmd
git add .
git commit -m "Add Jenkinsfile"
git push origin main
```

## Step 9: Add Docker Hub credential in Jenkins

1. Open `http://localhost:8080`
2. Manage Jenkins → Credentials.
3. Select Global credentials → Add Credentials.
4. Kind: **Secret text**
5. Secret: Docker Hub access token.
6. ID: `dockerhub-token`
7. Click Create.

## Step 10: Build Jenkins Pipeline

1. Jenkins → New Item.
2. Name: `Program10-Pipeline`.
3. Select Pipeline → OK.
4. Definition: **Pipeline script from SCM**.
5. SCM: Git.
6. Repository URL: `https://github.com/Aishwarya0625/Program10.git`
7. Branch: `*/main`
8. Script Path: `Jenkinsfile`
9. Save → Build Now.
10. Console Output alli `Finished: SUCCESS` check maadu.
