<script setup>
import { ref } from 'vue';

const showModel = ref(false)
</script>

<template>
  <header>
    <h1>transaction cource</h1>
  </header>

  <main class="main">
    <button @click="showModel = true">
        show model
    </button>
    <transition :duration="1400">
    
      <div v-if="showModel" class="model-wrapper">
        <div @click="showModel = false" class="model-bg">

        </div>
        <div class="model">
          <button class="model-close" @click="showModel = false">X</button>
          <div class="model-content">hello world</div>
        </div>
      </div>
    </transition>
  </main>
</template>

<style scoped>
.model-wrapper,
.model-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.model-bg{
  background: rgba(0, 0, 0, 0.4);
}
.model,
.model-bg{
  transition: all 1s ease;
}
.model {
  position: relative;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 1px 5px rgba(0, 0, 0, 0.2);
  padding: 20px;
  z-index: 2;
  
}
.model-close{
  position: absolute;
  top : 0;
  right: 1px;
  padding: 5px;
  appearance: none;
  background: none;
  border: none;
  font-size: 15px;

}
.v-enter-active .model{
  transition-delay: 0.4s;

}
.v-enter-from .model,
.v-leave-to .model{
  opacity: 0;
  transform: translateY(-30px);
}

</style>
