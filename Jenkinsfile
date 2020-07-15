pipeline {
    agent any

    stages {

        stage('master branch') {
            when { branch 'master' }
            steps {
                echo "This should print when git hook triggered by change to master branch"
            }
        }

        stage('git tag by pattern') {
            when { tag pattern: '.*tagtest.*', comparator: "REGEXP" }
            steps {
                echo "This should only print when git hook triggered by a git tag event!"
            }
        }

        stage('git tag') {
            when { tag '*tagtest*' }
            steps {
                echo "This should only print when git hook triggered by a git tag event!"
            }
        }

    }
}
