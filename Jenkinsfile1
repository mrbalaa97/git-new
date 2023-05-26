pipeline {
    agent any
    stages {
        stage ("1. install nginx") {
            steps {
                sh "sudo yum install -y nginx"
                sh "mkdir -p inbound"
                sh "mkdir -p outbound"
            }
        }
         stage ("2. service install") {
            steps {
                sh "sudo yum update -y"
                sh "sudo yum install -y docker"
            }
        }
        stage ("3. service start") {
            steps {
                sh "sudo systemctl restart docker"
                sh "sudo systemctl enable docker"
            }
        }
        stage ("4. nginx") {
            steps {
                sh "rpm -qa | grep nginx"
            }
        }
        stage ("5. create file") {
            steps {
                sh "echo test.txt"
                sh "date"
                sh "cal"
            }
        }
        stage ("6. create file") {
            steps {
                sh "echo test1.txt"
                sh "date"
                sh "cal"
            }
        }
        stage ("7. get inside folder") {
	    steps {
	            sh "sudo chmod -R 777 /home/ec2-user/"
                sh "cd /home/ec2-user/"
                writeFile(file: "/home/ec2-user/index.html", text: "this is besant website", encoding: "UTF-8") 
	     }
        } 	
    }
}
