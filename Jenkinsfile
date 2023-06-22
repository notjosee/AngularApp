pipeline{  
    agent any
  
    environment {
        lista = 'josecursoci@gmail.com'
    }
    stages{
        stage('Instalar Dependencias'){
            steps{
                sh 'npm install'
            }
        }

        stage('Compilacion del APP'){
            steps{
                sh 'npm run build'
            }
        }

        stage('Mostrar Archivos'){
            steps{
                sh 'ls -la'
            }
        }
    }
        post{
          always{
            emailext body: "Correo de prueba Jenkins", subject: "Prueba", to: '$Lista'

      }
    }
}
