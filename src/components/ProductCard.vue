<!-- ProductCard.vue - Mer komplex data -->
<script setup>
defineProps({
  product: {
    type: Object,
    required: true,
    // Validera objektets struktur
    validator: (value) => {
      return value.id && value.name && value.price
    }
  },
  tags: {
    type: Array,
    default: () => []  // VIKTIGT: Function för arrays/objects
  },
  inStock: {
    type: Boolean,
    default: true
  }
})
</script>

<template>
  <div class="product-card">
    <h3>{{ product.name }}</h3>
    <p class="price">{{ product.price }} kr</p>
    
    <div class="tags">
      <span v-for="tag in tags" :key="tag" class="tag">
        {{ tag }}
      </span>
    </div>
    
    <p v-if="!inStock" class="out-of-stock">
      Slutsåld
    </p>
  </div>
</template>

<style scoped>
.product-card {
  border: 1px solid #000000;
  padding: 1rem;
}
.price {
  font-size: 1.5rem;
  font-weight: bold;
  color: #007bff;
}
.tag {
  background: #000000;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  margin-right: 0.5rem;
  font-size: 0.75rem;
}
.out-of-stock {
  color: red;
  font-weight: bold;
}
</style>