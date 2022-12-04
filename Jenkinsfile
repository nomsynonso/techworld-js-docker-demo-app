pipeline {

    agent any
     parameters {
        choice(name: 'VERSION', choices: ['1.43.0', '1.43.1', '1.44.0' ], description: '' )
        booleanparam(name: 'monolithTests',defaultValue: true, description: '')
     }
    
    stages {
        stage("build"){
            steps {
                echo 'building the application...'
            }
        }
        
        stage("test"){
            when {
                expression {
                    params.monolithTests
                }
            }    
            steps {
                echo 'testing the application...'
            }
        }
        
        stage("deploy"){
            steps {
                echo 'deploying the application...'
                echo "deploying version ${params.VERSION}"
            }
        }
    }
}
