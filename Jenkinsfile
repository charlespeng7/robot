pipeline {
    agent any
    stages {
       stage('Build') {
             steps {
                echo '编译'
            }
        }
       stage('提交测试') {
          parallel {
             stage('代码分析'){
                steps {
                   echo '代码分析ing...'
                   echo '代码分析完成...'
                  }
              }
              stage('单元测试'){
                 steps {
                   echo '单元测试ing....'
                   echo '单元测试完成.....'
                   }
               }
           }
       }
        stage('验收阶段') {
          parallel {
              stage('环境测试'){
                 steps {
                    echo 'Test Module1--01 stage ...'
                    dir('/robot'){
                    sh 'pwd'
                    sh 'ls'
                    }
                  }
                }
              stage('接口测试') {
                 steps {
                    echo 'Test Module1--02 stage ...'
                    }
                }
               stage('UI自动化测试') {
                  steps {
                    echo 'Test Module1--03 stage ...'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
