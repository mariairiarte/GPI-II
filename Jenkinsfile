pipeline {
	agent any
    stages {
		stage('git') {
			steps { sh 'git clone https://github.com/mariairiarte/GPI-II' }
		}
		stage('Build') {
			steps {
				echo 'Compilar Simple'
				dir('SCCA/Integracion/simple') {
					sh 'mvn compile'
					sh 'mvn test'
					sh 'mvn site'
					sh 'mvn verify'
				}
				echo 'Compilar Android'
				dir('SCCA/AndroidApp/Application116511'){
					sh './gradlew'
				}
				echo 'Compilar Arduino'
				dir('SCCA/Sensores/FooProject'){ 
					sh 'make' 
				}
			}
		}
    }
}
