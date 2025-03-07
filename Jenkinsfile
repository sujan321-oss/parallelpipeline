// running a regression pipeline
// run it on an agent node  
def run_regression_pipeline(){
    echo "this function is running a regression pipeline "
    build job: "regressionpileine"  // Corrected syntax
}

// generating an error after 30 sec 
// run it on a master node 
def generate_error(){
    sleep(30)     
    echo "error generated successfully"
}

// Define tasks properly as closures
tasks = [ 
    "stage1" : {
        node("agent1") {
            stage("execute regression") { 
                run_regression_pipeline()
            }
        }
    },
    "stage2": {
        node("Built-In-Node") {
            stage("generate error") { 
                generate_error()
            }
        }
    }
]

// Execute the parallel tasks
parallel(tasks)
