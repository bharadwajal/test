node {
  

    stage 'Clone repository' {
  /* Let's make sure we have the repository cloned to our workspace */

       git url: 'https://github.com/bharadwajal/test-image.git'
    }

    

    stage('Test image') {
        /* Ideally, we would run a test framework against our image. */
        sh "docker exec -t trusting_fermat curl -s http://localhost:8000  > /tmp/result.txt  "
        out_result= readFile ' /tmp/result.txt '
        echo "Test result(${result.txt})"
        if ("${result.txt}" == "1")
        {
        echo "Http is listening on port 8000"
        sh "rm -f /tmp/result.txt"
        return true
        }

        else{
        echo "Http is not listening on port 80 yet"
		return false
        }

        }
    }

    
