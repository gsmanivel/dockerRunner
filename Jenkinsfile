pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull manivels1987/dockerpoc"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up smoke"
			}
		}
		stage("Scale Down"){
			steps{
				bat "docker-compose down"
			}
		} 		
	}
}
