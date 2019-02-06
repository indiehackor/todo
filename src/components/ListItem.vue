<template>
    <div>
        <span v-if="todo.done">X</span>
        {{todo.text}}
        <button
            v-if="!todo.done"
            @click="markDone(index)"
        >ferdig</button>
        <button @click="deleteItem(index)">slett</button>
    </div>
</template>

<script>
  export default {
    name : 'ListItem',
    props: ['todo', 'index'],
    methods: {
      deleteItem(index) {
        this.$emit('delete-todo', index)
      },
      markDone(index) {
        this.$emit('mark-as-done', index)
      }
    }
  }
</script>

<style scoped>

</style>
