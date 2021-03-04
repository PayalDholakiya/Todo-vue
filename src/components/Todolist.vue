<template>
  <div class="container">
    <h3>ToDo List</h3>
    <input
      v-model="newTodo"
      type="text"
      class="todo-input"
      placeholder="enter list item.."
      @keyup.enter="addTodo"
      style="height:25px"
    />
    <div class="list">
      <ul>
        <li class="todo-item" v-for="(todo, id) in todos" :key="todo.id">
          <span
            :class="{ active: todo.active }"
            v-on:click="toggleActive(todo)"
            >{{ todo.title }}</span
          >
          <span @click="deteleTodo(id)"><i class="fa fa-trash"></i></span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'todolist',

  data() {
    return {
      newTodo: '',
      todos: [
        {
          id: 1,
          title: 'xyz',
        },
      ],
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo == null) {
        alert('plese add item')
      }
      this.todos.push({
        id: this.id,
        title: this.newTodo,
      })
    },
    deteleTodo(id) {
      this.todos.splice(id, 1)
      console.log(id)
    },
    toggleActive(todo) {
      todo.active = !todo.active
      console.log(todo)
    },
  },
}
</script>
<style scoped>
h3 {
  color: rgb(68, 107, 107);
}
.container {
  width: 50%;
  text-align: center;
}
ul {
  text-align: center;
}
.list {
  width: 100%;
  margin-left: 10%;
}
li {
  display: inline-block;
  list-style: none;
  padding: 2px;
  cursor: pointer;
  width: 70%;
  border: 1px solid gainsboro;
}
li:nth-child(odd) {
  background-color: rgb(195, 195, 195);
}
li:nth-child(even) {
  background-color: gainsboro;
}
li:hover {
  background-color: gray;
}
.todo-input {
  width: 65%;
}
.todo-input:hover {
  background-color: gainsboro;
}
.todo-item {
  display: flex;
  justify-content: space-between;
}
.active {
  text-decoration: line-through;
}
</style>
