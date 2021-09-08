pipeline {
  agent any
  stages {
    stage('test'){
      steps{
        sh '''#!/bin/bash
        python3 -m venv test3
        source test3/bin/activate
        pip install pip --upgrade
        pip install pytest
        test.py --verbose --junit-xml results.xml sources/test_calc.py
        '''
     }
   post {
    always {
      junit 'result.xml'
     }
   }
  }
 }
}