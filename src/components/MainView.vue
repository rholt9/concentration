<template>
  <div class="main-view">
    <h1>{{ msg }}</h1>
    <input v-model="player" type="text" placeholder="Enter Player Name"/>
    <button v-on:click="enterWaitingRoom" :disabled="!player">Enter Waiting Room</button>
    <WaitingRoom v-show="waitingRoom" v-bind:user="player"/>
  </div>
</template>

<script>
import WaitingRoom from './WaitingRoom.vue'

export default {
  name: 'MainView',
  components: {
    WaitingRoom
  },
  props: {
    msg: String,
  },
  data: function () {
    return {
      player: '',
      waitingRoom: false
    }
  },
  methods: {
    enterWaitingRoom() {
      this.waitingRoom = true
      // render wating room
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
