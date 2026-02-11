<template>
 <section id="home" class="hero">
        <div class="hero-content">
            <h3>Hi, I'm</h3>
            <h1>Sezer <span id="name">Ünalmış</span></h1>
            <span class="typing-text">{{ displayText }}</span><br>
            <a href="#about" class="btn">More About Me</a>
        </div>
    </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';

// Reaktif değişkenler
const words = ["FullStack Developer", "Designer", "Researcher"];
const displayText = ref("");
const wordIndex = ref(0);
const charIndex = ref(0);
const isDeleting = ref(false);
const typeSpeed = ref(200);

const type = () => {
  const currentFullWord = words[wordIndex.value];

  if (isDeleting.value) {
    // Silme mantığı
    displayText.value = currentFullWord.substring(0, charIndex.value - 1);
    charIndex.value--;
    typeSpeed.value = 100;
  } else {
    // Yazma mantığı
    displayText.value = currentFullWord.substring(0, charIndex.value + 1);
    charIndex.value++;
    typeSpeed.value = 200;
  }

  // Durum geçişleri
  if (!isDeleting.value && charIndex.value === currentFullWord.length) {
    // Kelime tamamlandı, bekle ve silmeye başla
    isDeleting.value = true;
    typeSpeed.value = 2000;
  } else if (isDeleting.value && charIndex.value === 0) {
    // Kelime silindi, sonrakine geç
    isDeleting.value = false;
    wordIndex.value = (wordIndex.value + 1) % words.length;
    typeSpeed.value = 500;
  }

  // Fonksiyonu belirlenen hızda tekrar çağır
  setTimeout(type, typeSpeed.value);
};

// Bileşen yüklendiğinde animasyonu başlat
onMounted(() => {
  type();
});
</script>

<style scoped>
.typewriter-container {
  font-family: monospace; /* Karakter genişliklerinin eşit olması titremeyi azaltır */
  font-size: 1.5rem;
  display: flex;
  align-items: center;
}

.typing-text {
  color: #333;
  /* Yazının yanıp sönme animasyonu burada OLMAMALI */
}

.cursor {
  margin-left: 2px;
  width: 3px;
  background-color: #42b983;
  display: inline-block;
  /* Sadece imleç animasyonu */
  animation: blink 0.8s step-end infinite;
}

@keyframes blink {
  from, to { opacity: 1; }
  50% { opacity: 0; }
}
</style>