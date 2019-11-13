node('jenkins-slave-latex-centos7') {
    stage('Build') {
        git url: "https://github.com/ComputerScienceHouse/constitution-web.git"
	
	dir('constitution') {
            git url: 'https://github.com/ComputerScienceHouse/Constitution.git'
            sh "make"
            sh "mv articles.pdf ../articles.pdf"
            sh "mv bylaws.pdf ../bylaws.pdf"
        }

        dir('codeofconduct') {
            git url: 'https://github.com/ComputerScienceHouse/CodeOfConduct.git'
            sh "pdflatex csh-coc.tex"
            sh "mv csh-coc.pdf ../csh-coc.pdf"
        }

	sh "rm -rf constitution"
    sh "rm -rf codeofconduct"
    }

    stage('Start Build') {
        sh "oc start-build constitution-web --from-dir=./"
    }
}
