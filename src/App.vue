<template>
  <div id="container">
    <CatRoulette msg="Chat à la demande" />
  </div>
</template>

<script>
import CatRoulette from './components/CatRoulette.vue';
export default {
  name: 'App',
  components: {
    CatRoulette
  }
}
</script>

<style>
body {
  background-color: black;
  height: initial;
}

#app {
  margin-top: 5%;
  width: 100%;
  height: 95vh;
}

#container {
  /* border: 2px white solid; */
  width: 100%;
  height: 100%;

}
</style>
