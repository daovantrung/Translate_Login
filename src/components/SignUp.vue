<template>
  <img alt="Vue logo" src="../assets/logo.png">
  <div>Sign Up</div>
  <div class="register">
      <input v-model="username" type="text" name="" id="" placeholder="UserName">
    <input v-model="password" type="password" name="" id="" placeholder="Password">
    <button @click="signUp">SignUp</button>
    <p><router-link :to="{name:'login'}">Login</router-link></p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data(){
    return{
      username:'',
      password:'',
    }
  },
  methods:{
   async signUp(){
      let result = await axios.post('https://tooldich.nemosoftware.net/dichthuat/public/api/login',{
        username:this.username,
        password: this.password,
      });
      console.log(result);
      if(result.status == 200){
        localStorage.setItem('user-info',JSON.stringify(result.data))
        this.$router.push({name:'login'})
      }
    }
  },
  mounted(){
    let user = localStorage.getItem('user-info')
    if(user){
      this.$router.push({name:'home'})
    }
  }
}
</script>

<style >

</style>