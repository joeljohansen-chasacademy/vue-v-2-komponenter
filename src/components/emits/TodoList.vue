<!-- TodoList.vue -->
<script setup>
import { ref } from 'vue'
import TodoItemInteractive from './TodoItemInteractive.vue'

const todos = ref([
  { id: 1, text: 'Lära mig Vue', completed: false },
  { id: 2, text: 'Bygga komponenter', completed: false }
])

const toggleTodo = (id) => {
  const todo = todos.value.find(t => t.id === id)
  if (todo) todo.completed = !todo.completed
}

const deleteTodo = (id) => {
  todos.value = todos.value.filter(t => t.id !== id)
}

const editTodo = (id) => {
  console.log('Edit todo:', id)
  // Implementera edit-logik
}
</script>

<template>
  <div>
    <h2>Mina Todos</h2>
    <ul>
      <TodoItemInteractive 
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @toggle="toggleTodo"
        @delete="deleteTodo"
        @edit="editTodo"
      />
    </ul>
  </div>
</template>