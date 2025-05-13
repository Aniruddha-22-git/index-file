pipeline {
  agent {
    label{
            label "slave-1"
            //customWorkspace '/mnt/slave-1'
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
    }
}
