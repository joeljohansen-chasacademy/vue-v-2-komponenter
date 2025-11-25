<!-- TodoItem.vue - Enklaste varianten -->
<script setup>
// Array syntax - snabbt och enkelt
defineProps(['text', 'completed'])
</script>

<template>
  <li :class="{ completed }">
    {{ text }}
  </li>
</template>

<style scoped>
.completed {
  text-decoration: line-through;
  color: gray;
}
</style>