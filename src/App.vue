<template>
  <div id="app">
    <input v-model="text"/>
    <button @click="addTodo($event)">add</button>
    <ul>
      <li v-for="item in arrayTodos" :key="item.id">
        {{item.value}}
        <button @click="deleteTodo(item.id)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'App',
  methods: {
    addTodo({target}) {
      this.arrayTodos.length === 10 ? target.disabled = true 
                                    : this.arrayTodos.push({
                                                            id: this.arrayTodos.length,
                                                            value: this.text 
                                                            })
    },
    deleteTodo(id) {
      this.arrayTodos.splice(id,1)
    }
  },

  data() {
    return {
      text: '',
      arrayTodos: []
    }
  }
}
</script>

<style>

</style>
