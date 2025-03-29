pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                # Crear entorno virtual
                python3 -m venv jenv

                # Activar entorno virtual
                . jenv/bin/activate

                # Instalar paquetes en el entorno
                pip install --upgrade pip
                pip install pytest numpy pandas scikit-learn

                # Ejecutar pruebas
                pytest
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
