pipeline {
    agent any
    
    environment {
    DOCKERHUB_CREDENTIALS = credentials('docker-creds')
    DOCKER_ACCOUNT = 'chaitu685'
    }
    
    stages {
        
        stage('Git Checkout') {
            steps {
                git branch: 'feature', credentialsId: 'git-creds', url: 'https://github.com/TechITFactoryb01/online-boutique-microservices-code.git'
            }
        }

        stage('Docker Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        
        stage('Adservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/adservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:adservice-${BUILD_NUMBER}.0 ."
                    }   
                       
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o adservice-report.html --timeout 15m ${env.DOCKER_ACCOUNT}/test-repo1:adservice-${BUILD_NUMBER}.0
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:adservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "adservice-report.html",
                    reportName: "Trivy Adservice Report",
                ])
            }
        }
        
        stage('Cartservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/cartservice/src') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:cartservice-${BUILD_NUMBER}.0 ."
                    }                     
                       
                       
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o cartservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:cartservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:cartservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "cartservice-report.html",
                    reportName: "Trivy Cartservice Report",
                ])
            }
        }

        stage('Checkoutservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/checkoutservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:checkoutservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                              
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o checkoutservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:checkoutservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:checkoutservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "checkoutservice-report.html",
                    reportName: "Trivy Checkoutservice Report",
                ])
            }
        }

        stage('Currencyservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/currencyservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:currencyservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                              
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o currencyservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:currencyservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:currencyservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "currencyservice-report.html",
                    reportName: "Trivy Currencyservice Report",
                ])
            }
        }

        stage('Emailservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/emailservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:emailservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                             
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o emailservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:emailservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:emailservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "emailservice-report.html",
                    reportName: "Trivy Emailservice Report",
                ])
            }
        }

        stage('Frontend Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/frontend') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:frontend-${BUILD_NUMBER}.0 ."
                    }    
                        
                                              
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o frontend-report.html ${env.DOCKER_ACCOUNT}/test-repo1:frontend-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:frontend-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "frontend-report.html",
                    reportName: "Trivy Frontend Report",
                ])
            }
        }

        stage('Loadgenerator Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/loadgenerator') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:loadgenerator-${BUILD_NUMBER}.0 ."
                    }    
                        
                                              
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o loadgenerator-report.html ${env.DOCKER_ACCOUNT}/test-repo1:loadgenerator-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:loadgenerator-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "loadgenerator-report.html",
                    reportName: "Trivy Loadgenerator Report",
                ])
            }
        }

        stage('Paymentservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/paymentservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:paymentservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                             
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o paymentservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:paymentservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:paymentservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "paymentservice-report.html",
                    reportName: "Trivy Paymentservice Report",
                ])
            }
        }

        stage('Productcatalogservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/productcatalogservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:productcatalogservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                             
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o productcatalogservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:productcatalogservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:productcatalogservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "productcatalogservice-report.html",
                    reportName: "Trivy Productcatalogservice Report",
                ])
            }
        }

        stage('Recommendationservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/recommendationservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:recommendationservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                             
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o recommendationservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:recommendationservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:recommendationservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "recommendationservice-report.html",
                    reportName: "Trivy Recommendationservice Report",
                ])
            }
        }

        stage('Shippingservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/shippingservice') {
                        
                        sh "docker build -t ${env.DOCKER_ACCOUNT}/test-repo1:shippingservice-${BUILD_NUMBER}.0 ."
                    }    
                        
                                             
                       sh """
                       trivy image --format template --template "@/usr/local/bin/contrib/html.tpl" -o shippingservice-report.html ${env.DOCKER_ACCOUNT}/test-repo1:shippingservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh "docker push ${env.DOCKER_ACCOUNT}/test-repo1:shippingservice-${BUILD_NUMBER}.0"
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "shippingservice-report.html",
                    reportName: "Trivy Shippingservice Report",
                ])
            }
        }
        
        stage('Docker Images Cleanup') {
            steps {
                sh 'docker rmi -f $(docker images -q)'
            }
        }
        
        stage('Docker Logout') {
            steps {
                sh 'docker logout'
            }
        }
    }
}