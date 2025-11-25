<script setup lang="ts">
import { ref } from 'vue'
import TodoItemTyped from './TodoItemInteractiveTypeScript.vue'

interface Todo {
  id: number
  text: string
  completed: boolean
}

const todos = ref<Todo[]>([
  { id: 1, text: 'Lära mig Vue', completed: false },
  { id: 2, text: 'Bygga komponenter', completed: false }
])

const toggleTodo = (id: number): void => {
  const todo = todos.value.find(t => t.id === id)
  if (todo) todo.completed = !todo.completed
}

const deleteTodo = (id: number): void => {
  todos.value = todos.value.filter(t => t.id !== id)
}

const editTodo = (id: number): void => {
  console.log('Edit todo:', id)
}
</script>

<template>
  <div>
    <h2>Mina Todos (TypeScript)</h2>
    <ul>
      <TodoItemTyped 
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