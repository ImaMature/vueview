<template>
  <div class="home">
    <section id="mainBg" class="py-5 text-center container">
      <div id="mainCard" class="row py-lg-5">
        <div class="col-lg-6 col-md-8 mx-auto">
          <h1 class="fw-light">Album example</h1>
          <p id="mainText2" class="lead text-secondary">Something short and leading about the collection below—its contents, the creator,
            etc. Make it short and sweet, but not too short so folks don’t simply skip over it entirely.</p>
          <p>
            <a href="#" class="btn btn-primary my-2">Main call to action</a>
            <a href="#" class="btn btn-secondary my-2">Secondary action</a>
          </p>
        </div>
      </div>
    </section>

    <div class="album py-5 bg-light">
      <div class="container">
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
          <div class="col" v-for="(moc, idx) in state.arr" :key="idx">
            <Card :moc="moc"/>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import Card from '@/components/Card.vue';
import axios from "axios";
import { reactive } from 'vue';

export default {
  name: "MainHome",
  components: { Card },
  setup() {
    const state = reactive({
      arr: []
    })

    axios.get("/api/props").then(({data}) => {
      state.arr = data;
    })

    return {state}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="scss">
@import '@/assets/scss/main.scss'
</style>
