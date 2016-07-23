<template>
	 <div class="todo-list">
      <div v-for="item in items " >
        <list-item :item="item" ></list-item>
      </div>
    </div>
</template>

<script>
import ListItem from './list-item.vue'

export default {
  props: ['items'],

  methods: {
    
  },

  components: {
    ListItem
  }
}
</script>