pipeline{
agent any
stages{
stage('Download code'){
steps{
echo 'Code downloaded successfully'
}
}
stage('Build Application'){
steps{
sh 'mvn clean package -DskipTests'
}
}
stage('Build Docker')
{
steps{
sh 'docker build -t welcome-app .'
}
}
stage('Remove Old Container'){
steps{
sh 'docker rm -f welcome-container || true'
}
}
stage('Run Docker'){
steps{
sh 'docker run -d -p 8081:8081 --name welcome-container welcome-app'
}
}
stage('Verify Deployment'){
steps{
sh 'docker ps'
}
}
}
}
