
def toExecute=[:]

def data=[
   20:"khuma",
   10:"intern"
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

    data.each{
       echo "${itt}"
    }



   }


   
}




