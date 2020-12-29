<template>
  <div class='todo-list' id='todo-list-app'>
    <transition-group name='bounce' tag='div'>
      <div class='list-item' v-for='(item, index) in items' :key='item'>
        <div class='title'
             contenteditable='true'
             autocomplete='off'
             autocorrect='off'
             autocapitalize='off'
             spellcheck='false'
             tabindex='0'
             :title='messages.editTitle'
             @keyup='updateItem(index)'
             @blur='updateItem(index)'
             @paste='updateItem(index)'
             @delete='updateItem(index)'>{{ item.title }}</div>
        <div class='text'
             contenteditable='true'
             autocomplete='off'
             autocorrect='off'
             autocapitalize='off'
             spellcheck='false'
             tabindex='0'
             :title='messages.editText'
             @keyup='updateItem(index)'
             @blur='updateItem(index)'
             @paste='updateItem(index)'
             @delete='updateItem(index)'>{{ item.text }}</div>
        <div class='delete-button'
             tabindex='0'
             :title='messages.delete'
             @click='deleteItem(item)'
             @keyup.enter='deleteItem(item)'>
          <span class='fa fa-trash'></span>
        </div>
      </div>
    </transition-group>
    <div class='add-button'
         id='add-new'
         tabindex='0'
         :title='messages.add'
         @click='addNewItem'
         @keyup.enter='addNewItem'>
      <span class='fa fa-plus'></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "forms",
  data: {
    items: [
      {
        title: 'Learn Vue.js',
        text: 'Read the official guide and create a simple to-do list.'
      },
      {
        title: 'Publish learning results',
        text: 'Create a pen with the results'
      }
    ],
    messages: {
      delete: 'Delete this item',
      add: 'Add new item',
      editTitle: 'Edit title',
      editText: 'Edit text'
    }
  },
  methods: {
    addNewItem() {
      this.items.push({
        title: 'Your title here',
        text: 'Your text here'
      });
    },
    deleteItem(item) {
      let index = this.items.indexOf(item);
      this.items.splice(index, 1);
    },
    updateItem(index) {
      this.items[index].title = this.$el.querySelector('.title').innerText;
      this.items[index].text  = this.$el.querySelector('.text').innerText;
    }
  }
}
</script>

<style scoped>

</style>
