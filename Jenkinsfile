// Running a regression pipeline on an agent node
def run_regression_pipeline() {
    echo "This function is running a regression pipeline"
    build job: "regressionpipeline"  // Fixed syntax for job execution
}

// Generating an error after 30 seconds on the master node
def generate_error() {
    sleep(30)     
    error("Error occurred")
}

// Function to execute tasks in parallel on different nodes
def run_stages_parallely(nodelabel, task_to_execute) {
    node(nodelabel) {  
        stage("Execute Task") { 
            task_to_execute() // Execute the function (fixed)
        }
    }
}

// Define parallel tasks as closures
def tasks = [
    "stage1": { -> run_stages_parallely("agent1", run_regression_pipeline) }, 
    "stage2": { -> run_stages_parallely("", generate_error) } // "" for master node
]

// Run tasks in parallel
parallel(tasks)
