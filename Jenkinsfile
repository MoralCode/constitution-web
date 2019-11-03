node('jenkins-slave-latex-centos7') {
    stage('Build') {
        git url: "https://github.com/ComputerScienceHouse/constitution-web.git"
	
	dir('constitution') {
            git url: 'https://github.com/ComputerScienceHouse/Constitution.git'
            sh "make"
            sh "mv constitution.pdf ../articles.pdf"
        }

	sh "rm -rf constitution"
    }

    stage('Start Build') {
        sh "oc start-build constitution-web --from-dir=./"
    }
}
