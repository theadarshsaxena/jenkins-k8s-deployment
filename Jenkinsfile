pipeline {
  agent any
  stages {
    stage('CheckOut') {
      parallel {
        stage('CheckOut') {
          steps {
            sh '''pwd
sudo cp -r -v -f * /jendata'''
          }
        }

        stage('Debug') {
          steps {
            sh '''if ls /jendata | grep hello-world.txt
then
  echo "success"
else
  exit 1
fi'''
          }
        }

      }
    }

    stage('CheckPoint') {
      steps {
        echo 'Success'
      }
    }

    stage('k8s Launch') {
      steps {
        kubeconfig(serverUrl: 'https://34.65.189.167', credentialsId: 'ZXlKaGJHY2lPaUpTVXpJMU5pSXNJbXRwWkNJNklrcHBSMWwyUWpKUFdVbEhaVzVSVUZkRWFrWlpiRVJzZUc0emJXb3RlazR6UVRaWlVFZDFVeTFZU2xVaWZRLmV5SnBjM01pT2lKcmRXSmxjbTVsZEdWekwzTmxjblpwWTJWaFkyTnZkVzUwSWl3aWEzVmlaWEp1WlhSbGN5NXBieTl6WlhKMmFXTmxZV05qYjNWdWRDOXVZVzFsYzNCaFkyVWlPaUpyZFdKbExXNXZaR1V0YkdWaGMyVWlMQ0pyZFdKbGNtNWxkR1Z6TG1sdkwzTmxjblpwWTJWaFkyTnZkVzUwTDNObFkzSmxkQzV1WVcxbElqb2laR1ZtWVhWc2RDMTBiMnRsYmkwMk1uWTBiaUlzSW10MVltVnlibVYwWlhNdWFXOHZjMlZ5ZG1salpXRmpZMjkxYm5RdmMyVnlkbWxqWlMxaFkyTnZkVzUwTG01aGJXVWlPaUprWldaaGRXeDBJaXdpYTNWaVpYSnVaWFJsY3k1cGJ5OXpaWEoyYVdObFlXTmpiM1Z1ZEM5elpYSjJhV05sTFdGalkyOTFiblF1ZFdsa0lqb2lObVEzTmpoaE5XUXRObVptWWkwME1XUTVMVGhoWlRFdFl6QTVaak0zWlRnMVpHTXdJaXdpYzNWaUlqb2ljM2x6ZEdWdE9uTmxjblpwWTJWaFkyTnZkVzUwT210MVltVXRibTlrWlMxc1pXRnpaVHBrWldaaGRXeDBJbjAuWHVQaVZxQWN2M3FQVkV6Nk9jaXFvLVdWUHIwMTVlV21zcG4tb2ZnMzlmcWxQR2ZYdFFxa2htckJLWkNlQ09xM1VoVXgwYVRKMEdWQ29wMEdsZlkxcHVwNUNZWEJzbFM5SGZsYVpVWUZYNUxHSzRCamdkT1lJcVhIWXZ6cFZscHJfUXpWclBweGN1b2VIWElxVXhmVE10cVJfRnVuSlZGTTYzV3BoTXpNcTQyZkgxV2xXNHBfQWNvSU1xVWRsZkJsNkd3SDZBQ2ZNMzN2UVdLTUUySFFpeTB3LWVMSmJNWFd3VzFsRHVibDBKcXBrNDRzRW1lQ1NNdWNIekdVemtHM2EwckRUX2VMMVNhUkluS3hOZzlIeUlUTk5BT1NyWGVMUkdlOW5hV0ZHNGo0MWRCM0poekFsd3RGdXlBWWxPdXR5TFZ2ZVNVMTJkZTdPYVRtMUMwbWt3', caCertificate: 'LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURLekNDQWhPZ0F3SUJBZ0lSQU1KeEhhaFVuY2RlRUwvUWEvWVlRRUl3RFFZSktvWklodmNOQVFFTEJRQXcKTHpFdE1Dc0dBMVVFQXhNa1ltVXpORGc1TkRNdE5tSTVOUzAwWlRNMUxXRXpaakF0WldJeU5EQTRNelF5Wm1abQpNQjRYRFRJd01Ea3dOekE0TURreE0xb1hEVEkxTURrd05qQTVNRGt4TTFvd0x6RXRNQ3NHQTFVRUF4TWtZbVV6Ck5EZzVORE10Tm1JNU5TMDBaVE0xTFdFelpqQXRaV0l5TkRBNE16UXlabVptTUlJQklqQU5CZ2txaGtpRzl3MEIKQVFFRkFBT0NBUThBTUlJQkNnS0NBUUVBblhqZ1ptU1BFUkFxTXlKYkdKODVSaHVmT1J0UEtVd21qcGk4K3VQNApoNkRtQ2VRWmt1R2dDc0xWY2p2K2V6YUd5R3o4cWE4NldKYjFUMnlYeDk4Y2s0Q28zb0V3bXM5amJnZkxUc3M0CmFZTTNmZlVWVTZZY2krUG1ja1l1VVpJNmYzcnpmekFBejRuVUlqSURFa2p3Yi84S08rWkJaN2dKc2h6WWd3Z1UKY0FtaC9QM054NlRtNFJRL3prS0hDY2oxMk42TmNML3E4OWJLRm9xbEQxcFhFTGRUMDFJbUVaWmhUTEprWitsSgozR0NIRkhDZEk1M2daUkkyQnA1amk0TU1zenR0TFVUWFd0TDNrY2NwR3JzT0JVOTlWdHpXMHNBM05XYXlsTmRtCnFINWZ5WHFyd0tPR2YvZWdrK0V0aHA3S2lzaW5DL1UzeXg1TEp1L2pxWHk4NFFJREFRQUJvMEl3UURBT0JnTlYKSFE4QkFmOEVCQU1DQWdRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVTBtVjRqaE1GWjhTdApNOHU4bzdYSVI1RGNITDh3RFFZSktvWklodmNOQVFFTEJRQURnZ0VCQUNrWjZVM0ZJNGNxaVQ4UUFtdGgrTm1YCkd2K3V1eEFpbzk3aktKMGU4SjdRd1pqSmM2dlhwcHhQRVRPeTl1TXM3MjQzTTB3RVJrUHQ3dC9vbHhDaU5lU20KUDVlMGF3TUYzRmMxdUQ3SURQZklONXNicitWZkVsTXpwWXhyTmxHeUMwbHZ1alBZSGpncFMrRkR4TUpldW9PNAp0anV4aFluVkprbUIrTWs4aFNqN3Y4NVhVVmxuM1JMYVhxc1BaZ0I1YnJwTzQ5ZVRnck90QWRQc2poV3lSWnBuCjZGYU5xeWdSVWwweHUrd2ZNWXVrbnBBWWtCVzhyUjlMcG9FTkVibjBrdGlsdW84WVk3RUFNV1B3MzZoclQrWDAKdEdCbHg4T1dwUGVwWm4rRCtDSzZldlBvUVVOT1NSTjR6bE4wZCtFN1FCaWc2SXFQdk93QjcxNjdvU2k0ZUFnPQotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0tCg==')
      }
    }

  }
}