pipeline {
    agent any
      parameters {
        string(name: 'PARAM1', defaultValue: '0', description: 'param1')
        string(name: 'PARAM2', defaultValue: '', description: 'param2')
        string(name: 'PARAM3', defaultValue: '', description: 'param3')
      }
      stages {
        stage('build') {
            steps {
                sh 'echo PARAM1 = $PARAM1'
                sleep time: 120, unit: 'SECONDS'
                sh 'echo PARAM2 = $PARAM2'
                sleep time: 120, unit: 'SECONDS'
                sh 'echo PARAM3 = $PARAM3'
                jfPipelines()
            }
        }
      }
}

jfPipelines(
  outputResources: """[
    {
      "name": "jenkins_job_master",
      "content": {
        "passing": 1234,
        "failing": 0
      }
    }
  ]"""
)
