pipeline{
  agent any
  stages{
    stage('Checkout'){
      steps{
        git url:'https://github.com/kunal22823/DockerDemo.git',branch:'main'
      }
    }
    stage('Build of Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }
    stage('Stop the pre-running Image'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    stage('Run the Image'){
      steps{
        bat 'docker run -d -p 7000:80 --name mycont mywebsite'
      }
    }
  }
}
