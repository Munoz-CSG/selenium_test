pipeline {
    agent any

    stages {
        stage('setup_entorno') {
            steps {
                script {
                    if (isUnix()) {
                        sh '''
                            chmod +x setup_entorno.sh ejecutar_prueba.sh
                            ./setup_entorno.sh
                        '''
                    } else {
                        bat 'setup_entorno.bat'
                    }
                }
            }
        }

        stage('ejecutar_prueba') {
            steps {
                script {
                    if (isUnix()) {
                        sh './ejecutar_prueba.sh'
                    } else {
                        bat 'ejecutar_prueba.bat'
                    }
                }
            }
        }
    }
}