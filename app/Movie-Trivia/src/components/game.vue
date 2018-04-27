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
* {
    background-color: grey;
    font-family: 'Raleway', sans-serif;
    text-align: center;
   }

header {
padding: 15px;
}

h2 {
font-size: 50px;
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

.navbar {
display: flex;
justify-content: space-around;
}

.aboutContainer {
display: flex;
flex-flow: row;
justify-content: space-around;
}

.staffInfo {
display: flex;
flex-flow: column;
align-items: center;
padding: 20px;
}

.staffTag {
padding: 10px;
font-family: 'Fjalla One', sans-serif;
}

.subtitle {
font-style: italic;
}

.infoContainer {
display: flex;
flex-flow: column;
}

ol {
list-style-type: none;
}

li {
padding: 20px;
}

.footerBox {
float: right;
padding: 20px;
}

i {
padding: 4px;
margin: 0px 5px;
}

i:hover {
color: yellow;
}

.fa {
font-size: 40px;
}

.staffInfo img {
    width: 200px;
}

.gameScreenshot {
    display: flex;
    justify-content: space-around;
    margin: 40px;
}


.brochureTxt {
    display: flex;
    justify-content: center;
    padding: 80px;
    margin: 40px;
}

.statsTxt {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
}
</style>
