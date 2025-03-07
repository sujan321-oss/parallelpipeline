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

def run_stages_parallely(nodelabel, taskToExecute){
    node(nodelabel){
         stage("execute task") { 
               taskToExecute()  // Execute the passed closure
         }
    }
}

// Define tasks properly with closures
tasks = [ 
    "stage1" : { run_stages_parallely("agent1", { run_regression_pipeline() }) },
    "stage2" : { run_stages_parallely("Built-In-Node", { generate_error() }) }
]

// Execute the parallel tasks
parallel(tasks)
