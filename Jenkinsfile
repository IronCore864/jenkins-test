podTemplate(containers: [
    containerTemplate(name: 'golang', image: 'golang:1.18', command: 'sleep', args: '99d')
  ]) {

    node(POD_LABEL) {
        stage('Get a Golang project') {
            git url: 'https://github.com/IronCore864/jenkins-test.git', branch: 'main'
            container('golang') {
                stage('Build a Go project') {
                    sh '''
                    cd /go/src/github.com/ironcore864/jenkins-test && go run main.go
                    '''
                }
            }
        }
    }
}
