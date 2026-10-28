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
