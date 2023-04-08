pipeline{
	agent any
		stages{
				stage ('1-clone'){
          	when{
          branch 'dev'
          }          
          steps{
						checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'groupgit', url: 'https://github.com/AppGroup2/jenkinsproject2.git']])

						}	
					}
				stage('2-Group Parallel job'){
					parallel{
						stage('Teeto-sub-job-1'){
							when{
          branch 'uat'
          }          
          steps{
								sh 'lscpu'
								sh 'echo $SHELL'
							}
						}
						stage('Chris'){
								steps{
								sh '/home/ubuntu/christianbashscript.sh'
							}
						}
						stage('Yomi'){
							steps{
							sh '/home/ubuntu/yomiscript.sh'
							}
						}
					}
				}
				stage('3-Group Parallel job'){
					parallel{
						stage('Aubin'){
							steps{
								sh 'ls'
							}
						}
						stage('Afeez'){
							steps{
								sh 'pwd'
							}
						}
					}
				}
				stage('4-Group Parallel job'){
					parallel{
						stage('Olu'){
							when{
          branch 'main'
          }          
          steps{
								sh 'lscpu'
							}
						}
						stage('Tunde'){
							steps{
								sh 'pwd'
							}
						}
						
					}
				}
	

			}	



	}
