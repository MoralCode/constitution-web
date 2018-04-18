node('jenkins-slave-latex-centos7') {
    stage('Build') {
        git url: "https://github.com/ComputerScienceHouse/constitution-web.git"
	
	dir('constitution') {
            git url: 'https://github.com/ComputerScienceHouse/Constitution.git'
            sh "make"
            sh "mv articles.pdf ../articles.pdf"
            sh "mv bylaws.pdf ../bylaws.pdf"
        }

	sh "ls -la"
    }

    stage('Start Build') {
        sh "oc start-build constitution-web --from-dir=./"
    }
}
