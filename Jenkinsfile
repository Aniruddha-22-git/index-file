pipeline {
  agent {
    label{
            label "slave-1"
            customWorkspace '/mnt/hello'
    }
  }
    stages {
      stage ("stage 1"){
        steps {
          sh "sudo yum install httpd -y"
          sh "sudo systemctl start httpd "
          sh "echo 'hello world' | sudo tee /var/www/html/index.html"
          sh "sudo chmod -R 777 /var/www/html/index.html"
        }
      }
      stage ("sample-project"){
        steps{
          sh "sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.105/bin/apache-tomcat-9.0.105.zip -O /mnt/hello/apache-tomcat-9.0.105.zip"
          sh "sudo unzip /mnt/hello/apache-tomcat-9.0.105.zip"
          sh "sudo chmod -R 777 /mnt/hello/apache-tomcat-9.0.105"
          sh "sudo wget https://tomcat.apache.org/tomcat-6.0-doc/appdev/sample/sample.war -O /mnt/hello/apache-tomcat-9.0.105/webapps/sample.war"
          sh "sudo cd /mnt/hello/apache-tomcat-9.0.105/bin/ && .startup.sh"
        }
      }
    }
}
