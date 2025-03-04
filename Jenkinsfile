
def toExecute=[]

def parallelexecutefun=[:]

def data=[
   20:"khuma",
   10:"intern"
]

 def printfunction(key, toprint){
    sleep(key)
    echo " ${key}<-------->${toprint}"

    return "hello"
  }

  def runregressiontest(){
        echo "running a regression pipeline"
        build job: "regressionpileine"
  }

  parallelexecutefun["makeitfailed"] = {
     runregressiontest()
  }

    data.each{
  parallelexecutefun["execute : ${it.value}"] = {
    printfunction(it.key,it.value)
  }
}

 



node {

 

   parallel(
    parallelexecutefun
   )


   stage("print exectue"){
    echo "printing execute ${toExecute.toString()}"

    data.each{
       echo "${it}"
    }





   }


   
}




