<!-- UserCard.vue - Med type validation -->
<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  age: {
    type: Number,
    required: true,
    validator: (value) => value >= 0 && value <= 120
  },
  role: {
    type: String,
    default: 'User'
  }
})
</script>

<template>
  <div class="user-card">
    <h3>{{ name }}</h3>
    <p>Ålder: {{ age }}</p>
    <span class="role">{{ role }}</span>
  </div>
</template>

<style scoped>
.user-card {
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
}
.role {
  background: #007bff;
  color: white;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-size: 0.875rem;
}
</style>