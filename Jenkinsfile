// Running a regression pipeline on an agent node
def run_regression_pipeline() {
    echo "This function is running a regression pipeline"
    build job: "regressionpipeline"
}

// Generating an error after 30 seconds on the master node
def generate_error() {
    sleep(30)     
    error("Error occurred")
}

// Function to execute tasks in parallel on different nodes
def run_stages_parallely(nodelabel, task_to_execute) {
    node(nodelabel) {  // Use empty string "" for master node
        stage("Execute Task") { 
            task_to_execute()
        }
    }
}

// Define parallel tasks (use closures to avoid immediate execution)
def tasks = [
    "stage1": { -> run_stages_parallely("agent1", run_regression_pipeline) },
    "stage2": { -> run_stages_parallely("", generate_error) } // Use "" for master node
]

// Run tasks in parallel
parallel(tasks)
