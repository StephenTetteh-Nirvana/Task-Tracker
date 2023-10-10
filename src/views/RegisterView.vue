<template>
  <div class="container">
    <div class="image-box">
      <router-link to="/">
        <img src="../images/icons8-menu-64.png"/>
      </router-link>
    </div>
      <div class="header">
          <h1>Create Account</h1>
          <h3>Create an account to enjoy our services</h3>
      </div> 

      <form class="form" @submit.prevent>
        <div class="input-one">
          <input type="text" placeholder="Enter Email Address"/>
        </div>

        <div class="input-two">
         <input type="password" placeholder="Enter Password"/>
        </div>
      </form>
      <button>Sign Up</button>
  </div>
</template>

<script>
  export default {
    name:'LoginView',
    setup(){

    }
  }
</script>

<style scoped>
.container{
  height:100vh;
}
.image-box img{
  margin-top:30px;
}
.header{
  margin-left:10px;
}
.form{
  margin-left:30px;
  margin-top:80px;
}
input[type="text"]{
  padding:10px;
  width:80%;
}
input[type="password"]{
  padding:10px;
  width:80%;
}
.input-two{
  margin-top:20px;
}
button{
  text-align:center;
  padding:15px 50px;
  background-color:black;
  color:white;
  border:none;
  border-radius:20px;
  letter-spacing:2px;
  font-weight:bold;
  font-size:16px;
  margin-left:100px;
  margin-top:100px;
}

</style>

