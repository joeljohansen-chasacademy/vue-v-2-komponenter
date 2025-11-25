<!--
Övning: ItemList - Props och emits tillsammans
Skapa en lista-komponent som visar items och låter användaren ta bort dem.

Uppgifter:
- Definiera props: items (Array, required)
- Definiera emits: 'remove-item'
- Visa alla items i en lista (v-for)
- Varje item har en "Ta bort" knapp
- När knappen klickas, emittera 'remove-item' med itemets index

I denna fil skapar du ItemList-komponenten.
Skapa sedan en parent-komponent där du:
- Har en array med items (t.ex. ['Äpple', 'Banan', 'Päron'])
- Skickar items som prop till ItemList
- Lyssnar på 'remove-item' event
- Tar bort rätt item från arrayen när event emitteras
-->

<script setup lang="ts">
// TODO: Importera vad du behöver från vue

// TODO: Definiera props

// TODO: Definiera emits

</script>

<template>
  <div>
    <h3>Min lista:</h3>
    <!-- TODO: Loopa genom items med v-for -->
    <!-- Visa varje item och en "Ta bort" knapp -->
    
  </div>
</template>

<style scoped>
ul {
  list-style: none;
  padding: 0;
}

li {
  padding: 0.5rem;
  margin: 0.25rem 0;
  border: 1px solid #ddd;
  display: flex;
  justify-content: space-between;
}

button {
  background: #e74c3c;
  color: white;
  border: none;
  padding: 0.25rem 0.5rem;
  cursor: pointer;
}
</style>