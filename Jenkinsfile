node("jenkins-mahwahtech-test") {
  git branch: 'main', url: 'https://github.com/ryadama9/DINDTest.git'
        stage("Build"){
            container(name: 'buildah'){
                script {
                    //sleep 99999
                    sh "buildah build -t buildah-test:2 ."
                    sh "buildah tag buildah-test:2 buildah-test:latest"
                    sh 'buildah push buildah-test:latest quay.io/volvocars/test-kaniko:latest'
                    //sh "/kaniko/executor --dockerfile Dockerfile --context `pwd` --destination quay.io/volvocars/test-kaniko:latest"
                    }
                }
        }
}
