<template>
  <div class="wyr">

    <h2>Please make your choice!</h2>

    <h3>{{ question.prompt }}</h3>
    <!-- set vmodel and vbind to select only one radio, use value v-bind-->
    <input type="radio"
    v-model="answerUser.choice"
    v-bind:value="question.answer1"
    v-on:change="choiceMade">
    <label>{{question.answer1}}</label>

    <input type="radio"
           v-model="answerUser.choice"
           v-bind:value="question.answer2"
           v-on:change="choiceMade">
    <label>{{question.answer2}}</label>


  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: Object
  },

  data(){
    return {
        choice: ''
      }
  },
  ///method will display to parent
  methods:{
    choiceMade(){
      this.$emit('answer-changed', this.choice, this.question.id)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

.wyr {
  border: 6px chartreuse;
  background: indigo;
}

</style>
