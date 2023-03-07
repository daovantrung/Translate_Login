<template>
  <img alt="Vue logo" src="../assets/logo.png">
  <div>Login Page</div>
  <div class="login">
      <input v-model="username" type="text" name="" id="" placeholder="UserName">
    <input v-model="password" type="password" name="" id="" placeholder="Password">
    <button @click="login">Login</button>
    <p><router-link :to="{name:'signup'}">Sign Up</router-link></p>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data(){
    return{
      username:'',
      password:'',
    }
  },
  methods:{
   async login(){
      let result = await axios.get(`https://tooldich.nemosoftware.net/dichthuat/public/api/login?username=${this.username}&password=${this.password}`,{

      })
      if(result.status == 200 && result.data.length >0){
        localStorage.setItem('user-info',JSON.stringify(result.data[0]))
        this.$router.push({name:'login'})
      }
      console.log(result,this.username,this.password)
    }
  }
}
</script>

<style>

</style>