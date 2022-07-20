pipeline {
    agent any
    stages {
        stage("information") {
            steps {
                sh "printenv"
                echo "$GIT_BRANCH"
            }
        }
        stage("build") {
            steps {
                echo "build"
            }
        }
    }
}                                                                                                                                                                                                                                                                                  