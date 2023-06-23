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
          success {
             emailext body: "${cuerpo-correo} proceso exitoso", subject: "${titulo-correo}", to: "${lista}" 
          }
          failure {
          emailext body: "${cuerpo-correo2} hay errores que revisar", subject: "${titulo-correo}", to: "${lista}" 
          }

      }
}
