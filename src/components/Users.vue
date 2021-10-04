<template>
      <div class="panel-body">
     
     <div class="totalusers">
      <h4 style="color:white;">High Score</h4><br/>
      <hr size="1" width="100%" color="white"/>

      <div class="card-score" v-for="data in result" v-bind:key="data.id">
        <img :src="data.price"/>
              
           <h3>
            {{data.name}}
             
          </h3> 
          <h3>
            {{data.score}}
          </h3>
      </div>


     </div>
   
      <div class="panel">
        <h2 style="color:white; padding:15px; font-size:25px;">Users</h2>
        <hr size="1" width="100%" color="white"/><br/>

      <div class='card' v-for="user in result" v-bind:key="user.id">
        
       
        <img :src="user.price"/>
        <h3>
            {{user.name}}
             
          </h3>  
        
       </div>  
           
         
       

      </div>





      </div>
</template>

<script>
import axios from 'axios';
//import Score from 'Score.vue';

//var result = [];
export default {
 
      name:"Users",
       
       data(){
         return{
            result : [],
         }
       },
      mounted(){
             setTimeout(()=>{
    axios
      .get('https://internetbusinessstartup.000webhostapp.com/highscore.php')
      .then(response => {
      // console.log(response.data);
        //arrs.push(response.data);
        //users.push();
     // for(let i=0;i<=1;i++)
     // {
       for(var i in response.data)
          this.result.push( response.data[i]);
      //}


        //users.push()
      })},1000)

      }
}


 

 





</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .panel-body{
    display:flex;
    flex-direction:columns;
    justify-content:center;
    align-item:center;
    gap:20px;
  }
.panel{
  background: rgba(255, 255, 255, 0.2);
border-radius: 16px;
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
backdrop-filter: blur(5px);
-webkit-backdrop-filter: blur(5px);
border: 1px solid rgba(255, 255, 255, 0.3);
    width:340px;
    padding:10px;
    margin-top:30px;
     
    
  }
  .card{
    display:flex;
     flex-direction:row;
     color:white;
     padding:10px;
     gap:12px;
  }
.card img{
  width:100%;
   border-radius:50%;
   height : 50px;
   width:50px;
 
}

.card h3{
  padding:5px;
}
#highlight{
  background-color:lightpink 0.3;
}
.totalusers{
    backdrop-filter: blur(16px) saturate(180%);
    -webkit-backdrop-filter: blur(16px) saturate(180%);
    background-color: rgba(255, 255, 255, 0.15);
    border-radius: 12px;
    border: 1px solid rgba(209, 213, 219, 0.5);
    width:200px;
    height:350px;
    padding:10px;
    margin-top:30px;
}


.card-score{
    display:flex;
     flex-direction:row;
     color:white;
     padding:10px;
     gap:15px;
     font-size: 12px;
}
.card-score img{
  width:100%;
   border-radius:50%;
   height : 30px;
   width:30px;
}


@media only screen and (max-width: 733px) {
   .panel-body{
     flex-direction: column;
     justify-content: center;
     align-items: center;
   }  
}








</style>