pipeline {
    agent any
      parameters {
        booleanParam(name: 'PARAM1', defaultValue: '', description: 'param1')
        string(name: 'PARAM2', defaultValue: '', description: 'param2')
        booleanParam(name: 'PARAM3', defaultValue: '', description: 'param3')
      }
      stages {
        stage('build') {
            steps {
                sh 'echo PARAM1 = $PARAM1'
                sleep time: 2, unit: 'SECONDS'
                sh 'echo PARAM2 = $PARAM2'
                sleep time: 2, unit: 'SECONDS'
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
