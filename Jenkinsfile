node('jenkins-slave-latex-centos7') {
    stage('Build') {
	dir('constitution') {
            git url: 'https://github.com/ComputerScienceHouse/Constitution.git'
            sh "make"
            sh "mv articles.pdf ../articles.pdf"
            sh "mv bylaws.pdf ../bylaws.pdf"
        }
	
        git url: "https://github.com/ComputerScienceHouse/constitution-web.git"
    }

    stage('Start Build') {
        sh "oc start-build constitution-web --from-dir=./"
    }
}
