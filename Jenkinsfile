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

        stage('Compilacion del App'){
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
            emailext body: "Correo de prueba Jenkins", subject: "Prueba", to: "${lista}"
            echo 'siempre me voy a ejecutar...no matter what happens in the world :| '
          }
          success {
             echo 'El pipeline se ejecutó correctamente'
          }
          failure {
          echo 'El pipeline tuvo un fallo'
          }

      }
}
