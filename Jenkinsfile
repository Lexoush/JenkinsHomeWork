pipeline {
    agent {label 'master'}
    parameters {
        choice(
            name: 'LANGUAGE',
            choices: ['ALL', 'JAVA', 'PYTHON', 'C'],
            description: 'Select language'
        )
    }
    stages {
        stage('Print Selection') {
            steps {
                echo "Selected Language: ${params.LANGUAGE}"
            }
        }
        stage('Display File') {
            steps {
                script {

                    if (params.LANGUAGE == 'JAVA') {
                        sh 'cat HelloJAVA.java'
                    }

                    if (params.LANGUAGE == 'PYTHON') {
                        sh 'cat HelloPython.py'
                    }

                    if (params.LANGUAGE == 'C') {
                        sh 'cat HelloC.c'
                    }

                    if (params.LANGUAGE == 'ALL') {
                        sh '''
                            cat HelloJAVA.java
                            cat HelloPython.py
                            cat HelloC.c
                        '''
                    }
                }
            }
        }
    }
}
