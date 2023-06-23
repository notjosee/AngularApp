pipeline{  
    agent any
  
    environment {
        lista = 'josecursoci@gmail.com'
        cuerpo-correo = "El pipeline ${BUILD_URL} se creo sin problemas,"
        cuerpo-correo2 = "El pipeline ${BUILD_URL} experimento problemas,"
        titulo-correo = "Detalles pipeline ${BUILD_URL} STATUS"
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
