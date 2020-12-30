<template>
  <div>
  <select id="selectedQuestion" v-model="selected" v-for="answer in answers" >
    <option v-for="question in questions">
      {{ question }}
    </option>
  </select>
  </div>
</template>

<script>
export default {
  props:['questions','answers'],
  name:'section-selector',
  data(){
    return {
      selected:'',
      answers:this.answers
    }
  },
  methods: {

  }
}
</script>

<style scoped>

</style>
