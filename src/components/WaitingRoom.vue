<template>
  <div class="waiting-room">
    <h1>Waiting for Player 2</h1>
    <p>{{user}}</p>
    <button v-on:click="beginGame">Begin Game</button>
    <Game v-show="startGame" v-bind:users="players"/>
  </div>
</template>

<script>
import Game from './Game.vue'

export default {
  name: 'WaitingRoom',
  components: {
    Game
  },
  props: {
    user: String,
  },
  data: function () {
    return {
      players: [],
      startGame: false
    }
  },
  methods: {
    beginGame() {
      this.players.push(this.user)
      this.startGame = true
      // begin game
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
