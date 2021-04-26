<template>
  <div id="app">
    <h1>Would you rather???</h1>

    <li v-for="choice in choiceMade"> {{ choice }}</li>


    <would-you-rather
        v-for="question in questions"
        v-bind:key="question.id" v-bind:question="question"
        v-on:answer-changed="answerChanged"
    >
    </would-you-rather>

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
        questions:[
          {
            id:0,
            question: 'Would you rather the aliens that make first contact be robotic or organic?',
            answer1: 'robotic',
            answer2: 'organic',
          },
          {
            id: 1,
            question: 'Would you rather be able to type/text very fast or be able to read really quickly?',
            answer1: 'type/text',
            answer2: 'read quickly'
          },
          {
            id:2,
            question: 'Would you rather be really good at math or really good at sports?',
            answer1: 'math',
            answer2: 'sports',
          },
        ]
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
