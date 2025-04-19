<template>
  <div @click="handleClick">
    <audio ref="backgroundMusic" src="/audio/backsound.mp3" autoplay loop muted></audio>

    <slot />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const backgroundMusic = ref(null);

let hasClicked = ref(false);

onMounted(() => {
  document.addEventListener("visibilitychange", () => {
    if (document.visibilityState === "visible" && !hasClicked.value) {
      setTimeout(() => {
        playAudio();
      }, 200);
    }
  });
});

const playAudio = () => {
  const audio = backgroundMusic.value;
  audio.muted = false;
  audio.play().catch((err) => {
    console.warn("Autoplay diblokir:", err);
  });
};

const handleClick = () => {
  if (!hasClicked.value) {
    hasClicked.value = true;
    playAudio();
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
}
</style>