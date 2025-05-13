pipeline {
  agent {
    label{
            label "slave-1"
            customWorkspace '/mnt/slave-1'
    }
  }
    stages {
      stage ("stage 1"){
        steps {
          sh "yum install httpd -y"
          sh "systemctl start httpd "
          sh "echo 'hello world' >> /var/www/html/index.html"
          sh "chmod -R 777 /var/www/html/index.html"
        }
      }
    }
}
