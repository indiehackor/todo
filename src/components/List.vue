<template>
    <div>
        <list-item
            v-for="(item, index) in items"
            :todo="item"
            :index="index"
            :key="index"
            @delete-todo="removeItem"
            @mark-as-done="completeItem"
        />
    </div>
</template>

<script>
  import ListItem from './ListItem'

  export default {
    name      : 'List',
    props: ['items', 'removeItem', 'completeItem'],
    components: { ListItem }
  }
</script>

<style scoped>

</style>
