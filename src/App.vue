<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <div>
            <form @submit="addItem" action="">
                <label for="todo-input">Ny ting å huske</label>
                <input
                    id="todo-input"
                    type="text"
                    v-model="newItemText"
                >
                <button>Legg til</button>
            </form>
            <list
                :items="todoList"
                :remove-item="removeItem"
                :complete-item="completeItem"
            />
        </div>
    </div>
</template>

<script>
  import List from './components/List'

  export default {
    name      : 'app',
    components: {
      List
    },
    data() {
      return {
        newItemText: '',
        todoList   : [
          { text: 'Item one', done: false }
        ]
      }
    },
    methods   : {
      addItem() {
        if (this.newItemText) {
          this.todoList.push({ text: this.newItemText, done: false })
          this.newItemText = ''
        }
      },
      removeItem(index) {
        this.todoList.splice(index, 1)
      },
      completeItem(index) {
        this.todoList[index].done = true
      }
    }
  }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2C3E50;
        margin-top: 60px;
    }

    label {
        display: block;
    }
</style>
