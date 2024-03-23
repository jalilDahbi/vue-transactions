<script setup>
import { ref } from 'vue';

const showContent = ref(false)
</script>

<template>
  <header>
    <h1>transaction cource</h1>
  </header>

  <main class="main">
    <button @click="showContent = !showContent">
      {{ showContent ? "Hide" : "Show" }} Content
    </button>
    <transition>
      <ul v-if="showContent">
        <li>item1</li>
        <li>item3</li>
        <li>item3</li>
      </ul>
    </transition>
  </main>
</template>

<style scoped>
.main {
background-color: aqua;
padding: 20px;
border: 3px solid rgb(2, 62, 62);
border-radius: 10px;
min-height: 200px;
}
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease, transform  0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
.v-leave-to {
  opacity: 0;
  transform: translateY(10px);
}
</style>
