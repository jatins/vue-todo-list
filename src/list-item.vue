<template>
  <div class="list-item pure-g" v-bind:class="{'done': item.done}">
  	<div class="pure-u-2-3 item-content">{{item.content}} </div>
  	<div class="actions pure-u-1-3">
  	  <a class="action" v-show="!item.done" v-on:click="toggleDone(item)">done</a>
  	  <a class="action" v-show="item.done" v-on:click="toggleDone(item)">undo</a> |
  	  <a class="action remove" v-on:click="removeItem(item)">delete</a>
  	</div>
  </div>
</template>

<script>
export default {
  props: ['item'],
  methods: {
  }
}
</script>