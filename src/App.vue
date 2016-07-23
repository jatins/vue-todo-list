<template>
  <div id="app">
    <h1>{{ title }}</h1>
  <hr>
  
  <form class="pure-form pure-g">
    <input type="text" v-model="newItem" class="add pure-u-2-3">
    <a class="add-item btn pure-button pure-u-1-3" v-on:click="addItem">Add</a>
  </form>
  
    <div class="todo-list">
      <div v-for="item in items " class="list-item pure-g" v-bind:class="{'done': item.done}">
        <div class="pure-u-2-3 item-content">{{item.content}} </div>
        <div class="actions pure-u-1-3">
          <a class="action" v-show="!item.done" v-on:click="toggleDone(item)">done</a>
          <a class="action" v-show="item.done" v-on:click="toggleDone(item)">undo</a> |
          <a class="action remove" v-on:click="removeItem(item)">delete</a>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data () {
    return {
      newItem: '',
      title: 'Todo List App',
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
  }
}
</script>


<!-- CSS -->
<style>

</style>
