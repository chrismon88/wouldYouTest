<template>
  <div id="app">
    <h1>Would you rather???</h1>

    <would-you-rather v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
                      v-bind:answer2="wyrAnswer2"
    v-on:answer-changed="answerChanged"></would-you-rather>

    <p>{{ userSelectionMessage }}</p>

  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },


    data(){
      return{
        wyrQuestion: 'Would you rather the aliens that make first contact be robotic or organic?',
        wyrAnswer1: 'robotic',
        wyrAnswer2: 'organic',
        userSelectionMessage: ''

      }
    },
    methods:{
      answerChanged(choice){
        this.userSelectionMessage = `Thanks! you chose ${choice}`

      }
    }

}
</script>

<style>

body{
  background: black;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: beige;
  margin-top: 60px;

}
</style>
