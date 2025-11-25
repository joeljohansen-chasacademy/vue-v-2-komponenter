<!--
Övning 2: MusicPlayer - Bygg en musikspelare 🎵
Skapa en musikspelare-komponent som kommunicerar med parent via emits.

Uppgifter:
- Skapa en MusicPlayer-komponent som tar emot en låt som prop
- Props: song (Object med title, artist, duration), isPlaying (Boolean)
- Knappar: Play/Pause, Next, Previous, Like
- Emittera events till parent: 'play', 'pause', 'next', 'previous', 'like'
- Visa låtens titel, artist och duration
- Ändra knapp-ikon baserat på isPlaying (>/ eller || baserat på om låten är gillad)
- Visa hjärta för like (</3 eller <3 baserat på om låten är gillad)

Vad ni kommer behöva använda:
- defineProps() för song och isPlaying
- defineEmits() för alla events
- $emit() eller emit() för att skicka events
- v-if/v-else för att visa rätt ikon
- @click för knappar  

BONUS:
- Lägg till en volume slider som emittar 'volume-change' med värdet
- Lägg till progress bar som visar hur långt i låten man är
- Använd TypeScript för song interface

I denna fil skapar du MusicPlayer-komponenten. Skapa sedan en parent-komponent där du:
- Håller en array av låtar
- Håller koll på vilken låt som spelas (currentSongIndex)
- Hanterar play/pause/next/previous logik
- Håller koll på vilka låtar som är likade
-->

<script setup lang="ts">
// TODO: Definiera props
// Tips: song ska vara ett Object med { title, artist, duration, liked }
// const props = defineProps({
//   song: {
//     type: Object,
//     required: true
//   },
//   isPlaying: {
//     type: Boolean,
//     default: false
//   }
// })

// TODO: Definiera emits


// TODO: Skapa en funktion för att hantera play/pause


</script>

<template>
  <div class="music-player">
    <!-- TODO: Visa albumomslag (placeholder) -->
    <div class="album-art">
      song.title
    </div>

    <!-- TODO: Visa låtinformation -->
    <div class="song-info">
      <h2 class="song-title"><!-- song.title --></h2>
      <p class="artist"><!-- song.artist --></p>
      <p class="duration"><!-- song.duration --></p>
    </div>

    <!-- TODO: Kontroller -->
    <div class="controls">
      <!-- Previous knapp -->
      <button class="control-btn">
        previous
      </button>

      <!-- Play/Pause knapp -->
      <button class="control-btn play-btn">
        <!-- Visa > om inte playing, annars || -->
      </button>

      <!-- Next knapp -->
      <button class="control-btn">
        next
      </button>

      <!-- Like knapp -->
      <button class="control-btn like-btn">
        <!-- Visa <3 om liked, annars </3 -->
      </button>
    </div>

    <!-- TODO (Bonus): Volume slider -->
    <!-- <div class="volume">
      <span>vol</span>
      <input type="range" min="0" max="100" value="50">
    </div> -->
  </div>
</template>

<style scoped>
.music-player {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 2rem;
  border-radius: 20px;
  max-width: 400px;
  color: white;
  box-shadow: 0 10px 40px rgba(0,0,0,0.3);
}

.album-art {
  width: 200px;
  height: 200px;
  background: rgba(255,255,255,0.1);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  margin: 0 auto 1.5rem;
  backdrop-filter: blur(10px);
}

.song-info {
  text-align: center;
  margin-bottom: 1.5rem;
}

.song-title {
  font-size: 1.5rem;
  margin: 0 0 0.5rem 0;
}

.artist {
  font-size: 1rem;
  opacity: 0.9;
  margin: 0 0 0.25rem 0;
}

.duration {
  font-size: 0.875rem;
  opacity: 0.7;
  margin: 0;
}

.controls {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

.control-btn {
  background: rgba(255,255,255,0.2);
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all 0.3s;
  backdrop-filter: blur(10px);
}

.control-btn:hover {
  background: rgba(255,255,255,0.3);
  transform: scale(1.1);
}

.play-btn {
  width: 60px;
  height: 60px;
  font-size: 2rem;
  background: rgba(255,255,255,0.3);
}

.like-btn {
  font-size: 1.8rem;
}

.volume {
  margin-top: 1.5rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.volume input {
  flex: 1;
  cursor: pointer;
}
</style>