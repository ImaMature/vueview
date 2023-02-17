<template>

  <MainHeader/>
  <MainHome/>
  <MainFooter/>

</template>

<script>
import MainHome from "@/pages/Home.vue"
import MainFooter from "@/pages/Footer.vue"
import MainHeader from "@/pages/Header.vue"

export default {
  name: 'App',
  components:{
    MainHeader,
    MainHome,
    MainFooter
    
  }
}
</script>

<style>


</style>
