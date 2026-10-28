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


