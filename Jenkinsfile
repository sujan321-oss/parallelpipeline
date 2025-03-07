
// running a regression pieline
// run it on a agent node  
def run_regression_pipeline(){
    echo "this function is running a regression pipeline "
    buildjob : "regressionpipeline"
}


// generating a error after 30 sec 
// run it on a master node 
def generate_error(){
    sleep(30)     
    error("errror occured") 
}

tasks = [ 
        "stage1" : {run_stages_parallely("agent1",run_regression_pipeline())} ,
         "stage2": {run_stages_parallely("mastert",generate_error())},
]



def run_stages_parallely(nodelabel,task_to_excute){
    node(nodelabel){
         stage("exectue task") { 
               task_to_excute
         }
    }
}


parallel(
   tasks
)



