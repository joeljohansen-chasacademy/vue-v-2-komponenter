<!--
Övning: ClickButton - Enkel komponent med emits
Skapa en knapp-komponent som emittar olika events.

Uppgifter:
- Definiera props: label (String, default: "Klicka här")
- Definiera emits: 'click', 'double-click'
- En knapp som visar label-texten
- Vid vanligt klick: emittera 'click' event
- Vid dubbelklick: emittera 'double-click' event
- (Tips: använd @click och @dblclick)

I denna fil skapar du ClickButton-komponenten.
Skapa sedan en parent-komponent där du:
- Lyssnar på 'click' och 'double-click' events
- Visa meddelanden i parent när events emitteras
- T.ex. "Knappen klickades!" eller "Dubbelklick!"
-->

<script setup lang="ts">
// TODO: Importera vad du behöver från vue

// TODO: Definiera props

// TODO: Definiera emits

</script>

<template>
  <div>
    <!-- TODO: Skapa knapp som emittar events -->
    
  </div>
</template>

<style scoped>
button {
  padding: 0.5rem 1rem;
  cursor: pointer;
}
</style>