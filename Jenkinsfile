pipeline {
    agent any
    parameters{
        choice(name:'VERSION', choices:['1.1.0', '1.2.0','1.3.0'], description: '')
        booleanParam(name:'executeTests',defaultValue:true,description:'')
    }
    stages{
        stage('build'){
            steps{
                echo 'Building...'
                echo "Building version ${NEW_VERSION}"
            }
        }

        stage('test'){
            when{
                expression{
                    params.executeTests
                 }
            }
            steps{
                echo 'Testing...'
            }
        }
        
        stage('deploy'){
            steps{
                echo 'Deploying...'
                echo "Deploying version ${params.VERSION}"
            }
        }

       
    }
}
