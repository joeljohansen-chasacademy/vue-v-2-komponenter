<!--
Övning 1: MovieCard - Bygg ett filmkort
Skapa en komponent som visar information om en film med props.

Uppgifter:
- Skapa en MovieCard-komponent som tar emot props för filminfo
- Props: title (String, required), year (Number, required), genre (String, default: "Drama"), 
  rating (Number, 0-10, default: 0), posterUrl (String, default: "/placeholder-movie.jpg")
- Visa filmens titel, år, genre, och betyg med stjärnor (*)
- Om rating är över 8, visa en "Rekommenderad!"-badge
- Lägg till en "watched" prop (Boolean) som gör kortet gråskalat om filmen är sedd

Vad ni kommer behöva använda:
- defineProps() med objektsyntax för validering
- :class för dynamisk styling
- Computed properties för att beräkna antal stjärnor
- v-if för att visa badge

BONUS:
- Lägg till en validator för rating (0-10)
- Visa "Nyhet!" badge om year är samma som innevarande år
- Använd TypeScript för extra utmaning!

I denna fil skapar du komponenten. Skapa sedan en parent-komponent (t.ex. App.vue) 
där du importerar och använder MovieCard med olika filmer.
-->

<script setup lang="ts">
import { computed } from 'vue'

// TODO: Definiera props med defineProps()
// Tips: Använd objektsyntax för type, required, default
// const props = defineProps({
//   title: {
//     type: String,
//     required: true
//   },
//   ...
// })

// TODO: Skapa en computed property för att generera stjärnor
// Tips: Använd props.rating för att avgöra antal stjärnor

// TODO: (Bonus) Skapa computed för att kolla om filmen är ny


</script>

<template>
  <div class="movie-card">
    <!-- TODO: Visa poster-bild -->
    <div class="poster">
      <img alt="Movie poster">
    </div>

    <div class="content">
      <!-- TODO: Visa titel och år -->
      <h2><!-- title --> (<!-- year -->)</h2>

      <!-- TODO: Visa genre -->
      <p class="genre">Genre: <!-- genre --></p>

      <!-- TODO: Visa rating med stjärnor -->
      <div class="rating">
        <span class="stars"><!-- stjärnor här --></span>
        <span class="score"><!-- rating -->/10</span>
      </div>

      <!-- TODO: Visa "Rekommenderad!" badge om rating > 8 -->
      
      <!-- TODO: (Bonus) Visa "Nyhet!" badge om isNew -->
    </div>
  </div>
</template>

<style scoped>
.movie-card {
  border: 2px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  width: 300px;
  transition: transform 0.2s;
}

.movie-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}

.movie-card.watched {
  filter: grayscale(100%);
  opacity: 0.7;
}

.poster {
  width: 100%;
  height: 400px;
  background: #f0f0f0;
  overflow: hidden;
}

.poster img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.content {
  padding: 1rem;
}

h2 {
  margin: 0 0 0.5rem 0;
  font-size: 1.25rem;
  color: #333;
}

.genre {
  color: #666;
  font-size: 0.9rem;
  margin: 0.5rem 0;
}

.rating {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin: 0.5rem 0;
}

.stars {
  font-size: 1.2rem;
}

.score {
  font-weight: bold;
  color: #f39c12;
}

.badge {
  display: inline-block;
  padding: 0.25rem 0.75rem;
  border-radius: 12px;
  font-size: 0.75rem;
  font-weight: bold;
  margin-top: 0.5rem;
}

.recommended {
  background: #27ae60;
  color: white;
}

.new {
  background: #e74c3c;
  color: white;
}
</style>