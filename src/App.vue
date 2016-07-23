<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <hr>
  
    <form class="pure-form pure-g">
      <input type="text" v-model="newItem" class="add pure-u-2-3">
      <a class="add-item btn pure-button pure-u-1-3" v-on:click="addItem">Add</a>
    </form>
  
    <todo-list :items="items"></todo-list>
  </div>

</template>

<script>
import TodoList from './todo-list.vue'

export default {
  data () {
    return {
      newItem: '',
      title: 'Todo List',
      items: [
        {
          content: 'Get Milk',
          done: true
        }
      ]
    }
  },

  methods: {
    addItem() {
      this.items.push({content: this.newItem, done: false})
      this.newItem = ''
    },
    removeItem (item) {
      var index = this.items.indexOf(item)
      if (index !== -1) {
        this.items.splice(index, 1)
      }
    },
    toggleDone(item) {
      item.done = !item.done
    }
  },

  components: {
    TodoList
  }
}
</script>


<!-- CSS -->
<style>

</style>
