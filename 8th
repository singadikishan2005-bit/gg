deploy.yml:
---
- name: Deploy Maven Artifact
  hosts: localhost
  become: no

  tasks:
    - name: Create deployment directory
      file:
        path: /tmp/deployment
        state: directory
        mode: '0755'

    - name: Copy JAR file
      copy:
        src: "target/maven-example-1.0-SNAPSHOT.jar"
        dest: "/tmp/deployment/maven-example-1.0-SNAPSHOT.jar"

    - name: Run application
      shell: nohup java -jar /opt/deployment/maven-example-1.0-SNAPSHOT.jar > /dev/null 2>&1 &

hosts.ini:

[web]
localhost ansible_connection = local

pipeline code:

pipeline {
    agent any
    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/singadikishan2005-bit/devops.git'
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Deploy') {
            steps {
                sh 'ansible-playbook deploy.yml'
            }
        }
    }
}


