<template>
   <div id="app">

  <h1>Would you rather.......</h1>

  <would-you-rather
      v-for="question in questions"
      v-bind:id="question.id"
      v-bind:question="question.question"
      v-bind:answer1="question.answer1"
      v-bind:answer2="question.answer2"
      v-on:answer-changed="answerChanged"></would-you-rather>



  <h2>Which one would you pick? </h2>

  <p v-for="choice in choices"> {{choice}}</p>

   </div>

</template>


<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [
        {
          id: 0,
          question: 'Would you rather play soccer or football ',
          answer1: 'soccer',
          answer2: 'football',

        },
        {
          id: 1,
          question: 'what is you favorite food ',
          answer1: 'pizza',
          answer2: 'burger'
        },
        {
          id: 2,
          question: 'what is you favorite class you took ',
          answer1: 'Jave',
          answer2: 'web devloper'

        },
      ],
      choices: []

    }
  },
  methods: {


    answerChanged (id, choice) {
      this.choices[id] = choice
    }
  }
}
</script>

<style>

body {
  background: #8104f5
 }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #04fad0;
  margin-top: 60px;
  background: #00050c
}
</style>