
def toExecute=[]

def parallelexecutefun=[:]

def data=[
   20:"khuma",
   30:"intern"
]

 def printfunction(key, toprint){
    sleep(key)
    echo " ${key}<-------->${toprint}"

    if (key==30){
      echo "makeing ${key} faield"
      dss
    }

    return "hello"
  }

  def runregressiontest(){
        println "running a regression pipeline"
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
    parallelexecutefun + [failFast: true],

   )


   stage("print exectue"){
    echo "printing execute ${toExecute.toString()}"

    data.each{
       echo "${it}"
    }
    
   




   }


   
}




