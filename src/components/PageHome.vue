<template>
  <div>Page Home</div>
</template>

<script>
export default {
    mounted(){
    let user = localStorage.getItem('user-info')
    if(!user){
      this.$router.push({name:'login'})
    }
  }
}
</script>

<style>

</style>