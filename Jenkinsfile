pipeline{
    parameters{
        string(name: 'SOURCE_FILE',description: 'enter the webpage file',defaultValue: 'index.html')
        string(name: 'DESTINATION_FILE',description: 'enter the path file',defaultValue: 'index.nginx-debian.html')
        choice(name: 'SERVICE',choices:['nginx','apache','docker'],description: 'enter your service name')
    }
    agent any
    stages{
        stage('Build'){
            steps{
                sh """
                    echo "runing Build stage"
                    sudo cp ${params.SOURCE_FILE} /var/www/html/${params.DESTINATION_FILE}
                    echo "Build completed"
                """
            }
        }
        stage('Deploy'){
            steps{
                sh """
                    echo "runing Deploy stage"
                    sudo systemctl restart ${params.SERVICE}
                    echo "Deploy completed"
                """
            }
        }
    }
}
