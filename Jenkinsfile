def run_regression_pipeline() {
    echo "This function is running a regression pipeline"
    build job: "regressionpipeline"
}

def generate_error() {
    sleep(30)
    error("Error occurred")
}

def run_stages_parallely(nodelabel, task_to_execute) {
    node(nodelabel) {
        stage("Execute Task") { 
            task_to_execute() // Execute the function
        }
    }
}

// Define the tasks map properly
def tasks = [
    stage1: { -> run_stages_parallely("agent1", run_regression_pipeline) },
    stage2: { -> run_stages_parallely("", generate_error) }
]

// Execute in parallel
parallel tasks
