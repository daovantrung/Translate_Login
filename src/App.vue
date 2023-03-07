<template>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
.register input, .login input{
    padding: 10px 15px;
    margin: 10px 0px;
    width: 300px;
    border-radius: 5px;
}
.register, .login{
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
}
.register button, .login button{
    padding: 10px 15px;
    border-radius: 10px;
    background: antiquewhite;
}
</style>
