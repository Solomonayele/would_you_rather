<template>
<div class="wyr">

<h2> Please make your choice! </h2>

  <h3 v-bind:value="question"> {{ question }} </h3>

   <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade">
<label>{{answer1}}</label>

 <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade" >
<label>{{answer2}}</label>


 </div>

   <div>
 <h4> {{question2}}</h4>
 </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    id: Number,
    question: String,
    answer1: String,
    answer2: String,


  },
  data () {
    return {
      choice: ''
    }
  },
  methods: {
    choiceMade() {

      this.$emit('answer-changed', this.id, this.choice)
    }
  }
}
</script>


<style scoped>

h3 {
margin: 40px 0 0;
}

.wyr {
border: 2px #09ecc7 solid;
  background: black;
  margin: 10px;
}
</style>