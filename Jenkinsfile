pipeline {

	agent any
	
	options {
		disableConcurrentBuilds()
        //me falta mostrar marcas de tiempo y timeout de 5 minutos
	}

	parameters{
		integer(
			name: 'FORCE_COLOR',
			defaultValue: 0
		)
		booleanParam(
			name: 'NO_COLOR',
			defaultValue: true
		)

    
	stages{
		stage('Audit tools'){
            steps{
			    sh 'npm --version' 
                // imprimir la la versión de node con node --version.
            }
		}
		stage ('Install dependencies'){
            steps{
                sh 'npm install'
                //Incluye una etapa "Install dependencies" que instale las dependencias del proyecto con npm install.
            }
		}
		stage ('Format check'){
            //Incluye una etapa "Format check" que verifique el formato del código usando npm run format:check.
            steps{
                sh 'npm run format:check'   
            }
		}
		stage ('Code quality'){
            //Incluye una etapa "Code quality" que verifique la calidad del código usando npm run lint.
            steps{
                sh 'npm run lint'
            }
		}
		stage ('Type check'){
            //Implementa una etapa "Type check" que ejecute la comprobación de tipos con npm run type-check.
            steps{
                sh 'npm run type-check'
            }	
		}
		stage ('tests'){
            //Implementa una etapa "Tests" que ejecute los tests 			usando npm run test.
            steps{
                sh 'npm run test'
            }
		}
		stage ('Build'){
			//Implementa una etapa "Build" que construya la solución 			usando npm run build.
			//Esta etapa deberá de archivar los artefactos del 			directorio dist/. El fingerprint deberá estar activo.
			//Verifica que los artefactos son visibles. Deberás de 			ver dentro del job el archivo server.mjs.
            steps{
                sh 'npm run build'
                sh 'zip -r dist.zip dist'
                archiveArtifacts(artifacts: 'dist.zip', fingerprint:true)
            }
		}
	}
		
	}
    post {
        always{
            //Configura que cuando el job finalice, sin importar cómo, siempre limpie el workspace.
            cleanWs()
        }
        success{
            //Configura que cuando el job finalice exitosamente muestre por pantalla: 'Pipeline completed successfully!'.
            echo 'Pipeline completed successfully'
        }
        failure{
            //Configura que cuando el job finalice con errores muestre por pantalla: 'Pipeline failed. Review logs.'.
            echo  'Pipeline failed. Review logs'
        }
        
    }



}