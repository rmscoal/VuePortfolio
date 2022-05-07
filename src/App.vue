<script setup>
import About from './components/TheAbout.vue'
import Greetings from './components/Greetings.vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <Greetings msg="Hello!" />
      <Greetings msg="Welcome to my portfolio!" /> 
    </div> 
  </header>
  <main v-cloak>
    <About />
  </main>
</template>

<style>
@import './assets/base.css';

#app {
    margin: 0 auto;
    padding: 2rem;
}

header {
    line-height: 1.5rem;
    margin: 2rem auto;
}

main {
  height: inherit;
}
</style>