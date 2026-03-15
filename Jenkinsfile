pipeline {

agent any

tools {
maven 'maven3'
}

stages {

stage('Checkout') {
steps {
git 'https://github.com/yourusername/java-devops-pipeline.git'
}
}

stage('Build') {
steps {
sh 'mvn clean package'
}
}

stage('Docker Build') {
steps {
sh 'docker build -t yourdockerhub/java-devops .'
}
}

stage('Docker Push') {
steps {
sh 'docker push yourdockerhub/java-devops'
}
}

stage('Deploy') {
steps {
sh 'kubectl apply -f k8s/'
}
}

}

}
