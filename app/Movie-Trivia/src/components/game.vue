<template>
  <main>
    <div class="colContainer">
      <div class="col">
        <div class="div1">{{TheGame.Plot}}</div>
        <div id = "first" class="div2">
          <ul>
            <li>{{TheGame.Runtime}}</li>
            <li>{{TheGame.Directo}}</li>
            <li>{{TheGame.Actors}}</li>
          </ul>
        </div>
      </div>
      <div class="col">
        <div class="div1">{{TheGame.Year}}</div>
        <div id = "second" class="div2">
          <img :src='TheGame.Poster'>
        </div>
      </div>
      <div class="col">
        <div class="div1">{{TheGame.Genre}}</div>
        <div id = "third" class="div2">
          <ol>
            <li>Blade Runner</li>
            <li>Fifth Element</li>
            <li>Guardians of the Galaxy</li>
            <li>Star Wars: Return of the Jedi</li>
            <li>Total Recall</li>
            <li>Avatar</li>
            <li>Galaxy Quest</li>
          </ol>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  props: ["TheGame"]
  }
</script>

<style scoped>

</style>
