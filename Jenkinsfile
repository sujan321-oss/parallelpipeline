
def toExecute=[]

def data=[
   10:"khuma",
   20:"intern"
]

 def printfunction(key, toprint){
    sleep(key)
    echo " ${key}<-------->${toprint}"
  }



node {

 

   parallel(
     exec: {

          data.each{ key,value->
        toExecute.add(printfunction(key,value))
        }

     }
   )


   stage("print exectue"){
    echo "printing execute ${toExecute.toString()}"
   }


   
}




