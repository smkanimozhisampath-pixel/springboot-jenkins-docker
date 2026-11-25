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
stage('Run Docker'){
steps{
sh 'docker rm -f welcome-container || true'
sh 'docker run -d -p 8081:8080 --name welcome-container welcome-app'
}
}
}
}
