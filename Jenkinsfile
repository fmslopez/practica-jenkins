pipeline {

	agent any
	
	options {
		disableConcurrentBuilds()
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

			sh 'npm --version' // imprimir la la versión de node con node --version.

		}
		stage ('Install dependencies'){
			//Incluye una etapa "Install dependencies" que instale 			las dependencias del proyecto con npm install.

		}
		stage ('Format check'){
			//Incluye una etapa "Format check" que verifique el 			formato del código usando npm run format:check.

		}
		stage ('Code quality'){
			//Incluye una etapa "Code quality" que verifique la 			calidad del código usando npm run lint.

		}
		stage ('Type check'){
			//Implementa una etapa "Type check" que ejecute la 			comprobación de tipos con npm run type-check.

		}
		stage ('tests'){
			//Implementa una etapa "Tests" que ejecute los tests 			usando npm run test.

		}
		stage ('Construccion y archivado'){
			//Implementa una etapa "Build" que construya la solución 			usando npm run build.
			//Esta etapa deberá de archivar los artefactos del 			directorio dist/. El fingerprint deberá estar activo.
			//Verifica que los artefactos son visibles. Deberás de 			ver dentro del job el archivo server.mjs.
		}
		stage ('etapas finales'){
			//Configura que cuando el job finalice exitosamente 			muestre por pantalla: 'Pipeline completed 				successfully!'.
			//Configura que cuando el job finalice con errores 			muestre por pantalla: 'Pipeline failed. Review logs.'.
			//Configura que cuando el job finalice, sin importar 			cómo, siempre limpie el workspace.
		}



	}
		
	}



}