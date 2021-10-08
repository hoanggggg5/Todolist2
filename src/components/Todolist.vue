<template>
<div>
  <div class="todo-list">
    <TodoItem v-for="(todo, index) in todos" :key="index" :todo="todo" @item-completed="markComplete" @update-item="updateTodo" @delete-item="deleteTodo" />
  </div>
  <AddTodo @add-todo="addTodo" :idMax="todos.length > 0 ? todos[todos.length-1].id : 1" />
</div>
</template>

<script lang="ts">
import {
  Component,
  Vue
} from 'vue-property-decorator';
import TodoItem from './TodoItem.vue';
import AddTodo from './AddTodo.vue';

@Component({
  components: {
    TodoItem,
    AddTodo,
  },
})
export default class Todolist extends Vue {
  todos: Array < Todo > = [];
  markComplete(id: number) {
    this.todos = this.todos.map(todo => {
      if (todo.id === id) todo.completed = !todo.completed
      return todo
    })
  }
  updateTodo(id: number, updateTodo: string) {
    this.todos = this.todos.map(todo => {
      if (todo.id === id) todo.title = updateTodo
      return todo
    })
  }
  deleteTodo(id: number) {
    const index = this.todos.findIndex(todo => id !== todo.id)
    this.todos.splice(index, 1)
  }
  addTodo(newTodo: Todo) {
    this.todos.push(newTodo)
    console.log(this.todos)
  }
}
</script>

<style lang="css">
.todo-list {
  margin: 30px 0;
}

.flex {
  display: flex;
}
</style>
