<template>
  <div>
    <select id="selectedQuestion" v-model="selected" @change="onChange($event)">
      <option v-for="question in questions">
        {{ question }}
      </option>
    </select>
    <div v-if="selected === questions.age">
      <ageInput :answer="answer"
                v-for="answer in answers.age"
                :key="answers.age.length"></ageInput>
      <button @click="addForm($event)" id="addAge">addAgeForm</button>
    </div>
    <div v-if="selected === questions.cardType">
      <typeSelector :cardType="cardType"
                    v-for="cardType in answers.type"
                    :key="answers.type.length"></typeSelector>
      <button @click="addForm($event)" id="addType">addTypeForm</button>
    </div>
    <div v-if="selected === questions.cardStatus">
      <statusSelector :cardStatus="cardStatus"
                      v-for="cardStatus in answers.status"
                      :key="answers.status.length"></statusSelector>
      <button @click="addForm($event)" id="addStatus">addStatusForm</button>
    </div>
    <button @click="checkSelector">CHUDO BTN</button>
  </div>
</template>

<script>
import ageInput from "~/components/ageInput";
import typeSelector from "~/components/typeSelector";
import statusSelector from "~/components/statusSelector";
import sectionSelector from "@/components/sectionSelector";
export default {
  components: {
    ageInput,
    typeSelector,
    statusSelector,
    sectionSelector
  },
  data() {
    return {
      selected: '',
      questions: {
        age: 'Возраст',
        cardType: 'Тип карты',
        cardStatus: 'Статус карты'
      },
      sections:{
        age:{},
        cardType:{},
        cardStatus:{}
      },
      cardType: ['Gold', 'silver', 'bronze', 'iron'],
      cardStatus: ['Active', 'Disable', 'Blocked'],
      answers: {
        age: [],
        type: [],
        status: []
      }
    }
  },
  methods: {
    checkSelector() {
      console.log(this.selected)
    },
    onChange(evt) {
      console.log(evt.target.value)
      switch (evt.target.value) {
        case 'Возраст':
          console.log(this.selected)
          this.answers.age.push(evt.target.value)
          // this.sections.age.push(evt.target.value)
          break
        case 'Тип карты':
          this.answers.type.push(this.cardType)
          break
        case 'Статус карты':
          this.answers.status.push(this.cardStatus)
          break
      }
      console.log(evt.target.value)
      console.log(this.answers.age);
    },
    addForm(event) {
      console.log(this.answers.age.length)
      console.log(event.target.id)
      switch (event.target.id) {
        case 'addAge':
          this.answers.age.push(this.answers.age[0])
          break
        case 'addType':
          this.answers.type.push(this.answers.type[0])
          break
        case 'addStatus':
          this.answers.status.push(this.answers.status[0])
          break
      }
      //   console.log(event.target.id)
      //   console.log(this.answers.age)
      // this.answers.age.push(this.answers.age[0])
      //     id: this.questions.age.length+1,
      //     title: this.questions.age,
      //     isComplete: false
      //   });
    },
    deleteItem(item) {
      let index = this.items.indexOf(item);
      this.items.splice(index, 1);
    },
    updateItem(index) {
      this.items[index].title = this.$el.querySelector('.title').innerText;
      this.items[index].text = this.$el.querySelector('.text').innerText;
    }
  },

}
</script>

<style scoped>

</style>
