<template>
  <main>
    <div class="colContainer">
      <div class="col">
        <div class="div1">{{TheGame.Plot}}</div>
        <div id = "first" class="div2">
          <ul>
            <li v-if="Hints > 0">{{TheGame.Runtime}}</li>
            <li v-if="Hints > 1">{{TheGame.Director}}</li>
            <li v-if="Hints > 2">{{TheGame.Actors}}</li>
          </ul>
        </div>
      </div>
      <div class="col">
        <div class="div1">Year : {{TheGame.Year}}</div>
        <div id = "second" class="div2">
           <!-- <img v-if="Win":src='TheGame.Poster'> I hate this img. -->
          <p v-if="Win">You win nerd, gratz.</p>
        </div>
      </div>
      <div class="col">
        <div class="div1">{{TheGame.Genre}}</div>
        <div id = "third" class="div2">
          <ol>
            <li @click="getAHint">Blade Runner</li>
            <li @click="getAHint">Fifth Element</li>
            <li @click="winTheGame">Guardians of the Galaxy</li>
            <li @click="getAHint">Star Wars: Return of the Jedi</li>
            <li @click="getAHint">Total Recall</li>
            <li @click="getAHint">Avatar</li>
            <li @click="getAHint">Galaxy Quest</li>
          </ol>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  props: ["TheGame"],
  methods: {
  winTheGame: function() {
    this._data.Win = true
  },
  getAHint: function() {
    this._data.Hints += 1
    return this._data.Hints
  }
},
  data(){
    return {
      Win: false,
      Hints: 0
    }
  }
}
</script>

<style scoped>
  img {
    display: none;
  }
  .colContainer{
   display: flex;
   flex-flow: row;
   align-items: center;
   justify-content: space-around;
   padding: 20px;
  }

  .col {
   border: 1px black solid;
  }

  div {
   border: 1px black dotted;
  }

  .div1 {
   padding: 10px;
   margin: 10px;
   height: 100px;
   width: 300px;
  }

  .div2 {
   padding: 10px;
   margin: 10px;
   height: 600px;
   width: 300px;
  }
</style>
