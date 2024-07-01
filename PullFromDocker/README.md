# Pipeline for pulling image from Docker Hub

```
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Pull the Docker image
                    sh 'docker pull hello-world'

                    // Run the Docker container and store output in variable
                    def output = sh(script: 'docker run hello-world', returnStdout: true).trim()
                    
                    // Print the output of the Docker container
                    echo "Container output: ${output}"
                }
            }
        }
    }
}

```

## Explaination - 


1. Pipeline Setup:
   ```
   pipeline: Defines a Jenkins Declarative Pipeline.
   ```
2. Agents:
   ```
   agent any: Executes the pipeline on any available agent (Jenkins node).
   ```
3. Stages:
   ```
   Build: Defines a single stage named "Build" for simplicity.
   ```
4. Steps:
    ```
    script: Executes a block of scripted Pipeline code.
    
    sh 'docker pull hello-world':
    runs command in shell.
    This command pulls the hello-world Docker image from Docker Hub if not available locally.

    def output = sh(script: 'docker run hello-world', returnStdout: true).trim():
    Runs the hello-world Docker container using the sh step and stores output in variable 'output'.
    
    returnStdout: true : captures the standard output of the docker run command.
    .trim() : removes any leading/trailing whitespace from the output.

    echo "Container output: ${output}":
    Prints the output of the Docker container to the Jenkins console log.
    
    ```
