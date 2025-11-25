<!-- TodoItemInteractive.vue - Med events -->
<script setup>
defineProps({
  todo: {
    type: Object,
    required: true
  }
})

defineEmits(['toggle', 'delete', 'edit'])
</script>

<template>
  <li class="todo-item">
    <input 
      type="checkbox" 
      :checked="todo.completed"
      @change="$emit('toggle', todo.id)"
    >
    <span :class="{ completed: todo.completed }">
      {{ todo.text }}
    </span>
    <div class="actions">
      <button @click="$emit('edit', todo.id)">Edit</button>
      <button @click="$emit('delete', todo.id)">Delete</button>
      <!-- <button @click="$emit('complete', todo.id)">Done!</button> -->
    </div>
  </li>
</template>

<style scoped>
.todo-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem;
  border: 1px solid #eee;
  margin-bottom: 0.5rem;
}
.completed {
  text-decoration: line-through;
  color: gray;
}
.actions {
  margin-left: auto;
}
button {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1.2rem;
}
</style>