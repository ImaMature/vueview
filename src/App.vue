<template>
  <MainHeader />
  <MainHome />
  <MainFooter />
</template>

<script>
import MainHome from "@/pages/Home.vue"
import MainFooter from "@/components/Footer.vue"
import MainHeader from "@/components/Header.vue"

export default {
  name: 'App',
  components: {
    MainHeader,
    MainHome,
    MainFooter

  }
}
</script>

<style></style>
