<template>
  <div id="app">
    <h1>{{ title }}</h1>
  <hr>
  
  <form class="pure-form pure-g">
    <input type="text" v-model="newItem" class="add pure-u-2-3">
    <a class="add-item btn pure-button pure-u-1-3" v-on:click="addItem">Add</a>
  </form>
  
    <div class="todo-list">
      <div v-for="item in items" class="list-item pure-g">
        <div class="pure-u-2-3">{{item}} </div>
        <a class="pure-button remove pure-u-1-3" v-on:click="removeItem(item)">delete</a>
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
        'Get Milk',
      ]
    }
  },

  methods: {
    addItem() {
      this.items.push(this.newItem)
    },

    removeItem (item) {
      var index = this.items.indexOf(item)
      if (index !== -1) {
        this.items.splice(index, 1)
      }
    }
  }
}
</script>


<!-- CSS -->
<style>

</style>
