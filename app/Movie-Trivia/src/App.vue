<template>
  <div id="app">
    <TheHeader/>
    <TheGame :TheGame="TheGame"/>
  </div>
</template>

<script>
import TheHeader from "./components/header.vue"
import TheGame from "./components/game.vue"

export default {
  name: 'App',
  components: {
    TheHeader,
    TheGame
  },
  data(){
  return {
    TheGame: {}
  }
},
  mounted(){
      fetch("http://www.omdbapi.com/?i=tt3896198&apikey=28fb5af8")
      .then(response => {
        return response.json()
      })
      .then(response => {
        this.TheGame = response
      })
    }
}
</script>

<style>

</style>
