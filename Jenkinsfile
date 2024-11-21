def results() {
    data3 = "${params.mark}"
    int data4 = "$data3".toInteger()
    data7 = 63
    data5 = data7*data7
    return data5
}

def get_results() {
    data3 = "${params.mark}"
    int data4 = "$data3".toInteger()
    data8 = 63
    if(data8 >= 50){
        return "pass"
    }else{
        return "fail"
}
}

def myParam1 = "param1.yaml"
pipeline {
    agent any
    
    environment{
        testbed = "dev21.yaml"
        paramfile = "school_params.json"
        mark="${params.mark}"
        mydata = results()
        exam_results = get_results()

    }
    
    parameters{
     string(name: 'script_name', defaultValue: "shop.py", description: 'just for test')
     string(name: 'env_name', defaultValue: "STG", description: 'just for test')
    }
    
    stages {
        stage('Build') { 
            steps {
                println(mydata)
                /*echo "${params.script_name}  script_name"
                echo "${params.env_name}  env_name"
                echo "${env.WORKSPACE}  work space name"*/
                echo "$mydata This is Build stage."
            }
        }
        stage('Test') { 
            steps {
                script{
                    echo "$mark This is Test stage." 
                    
                    int mark = "$mark".toInteger()
                    total = mark + mark
                    echo "$mark This is Test stage." 
                    echo "$total This is total." 
                    
                }
                echo "$mark This is Test stage." 
            }
        }
        stage('Deploy') { 
            steps {
                //exam_results = get_results()
                echo "the result is $exam_results"
                echo "${env.testbed} This is Deploy stage." 
                echo "$myParam1 This is Deploy stage." 
            }
        }
    }
}
