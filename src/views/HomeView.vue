<template>
  <div class="container">
      <div class="header-section">
        <h1>Task Manager</h1>
        <button @click="Show">
          <img src="../images/icons8-menu-64.png"/>
        </button>
      </div>

      <div class="info" v-if="displayInfo">
        <p>With this task tracker web app u can create tasks,
          edit tasks and even delete tasks when u are done. 
        </p>
      </div>

      <div class="center-box">
          <router-link to="/login">
            <button class="login">Login</button>
          </router-link>

         <router-link to="/register">
          <button class="create">Create Account</button>
         </router-link>
    
      </div>


      <footer>
        <h2>CopyRight&copy;2023</h2>
      </footer>
  </div>
</template>

<script>
import {ref} from 'vue'
  export default {
     name:'HomeView',

     setup(){

      const displayInfo = ref(true);

      function Show(){
             displayInfo.value = !displayInfo.value;
      }

      return{
        displayInfo,
        Show
      }

     }
  }
</script>

<style scoped>
.container{
  height:100vh;
}
.header-section{
  display:grid;
  grid-template-columns:3fr 1fr;
}
.header-section h1{
  font-size:40px;
  margin-left:10px;
}
.header-section button{
  background:transparent;
  border:none;
}
.header-section img{
  width:50px;
}
.info{
   border:1px solid black;
   border-radius:15px;
}
.info p{
  font-size:18px;
  padding-left:20px;
}

.center-box{
 text-align:center;
 margin-top:40px;
}
.login{
  padding:10px;
  width:200px;
  border:1px solid black;
  background:transparent;
  font-size:18px;
  border-radius:20px;
}
.create{
  padding:10px 40px;
  border:1px solid black;
  background:transparent;
  font-size:18px;
  border-radius:20px;
  margin-top:20px;
}
footer{
  text-align:center;
  margin-top:40px;
}

</style>