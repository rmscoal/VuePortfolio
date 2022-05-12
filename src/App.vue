<script>
import About from './components/TheAbout.vue'
import Greetings from './components/Greetings.vue'
import Navi from './components/NavGuide.vue'

export default {
  components: {
    About,
    Greetings,
    Navi
  },
  data () {
    return {
      msgh1: ["Hello,", "Ola,", "Hai,"],
      msgh2: ["Welcome to my personal portfolio!", "Welcome to my little project!", 
      "Welcome to my Vue application!"]
    }
  },
  mounted () {

  },
  created () {

  }
}
</script>

<template>
  <Navi />
  <div class="main-wrapper">
    <Greetings :msgh1="msgh1" :msgh2="msgh2"/>
    <main>
      <About id="greeting"/>
    </main>
  </div>
</template>

<style>
@import './assets/base.css';

#app {
  margin: 0 auto;
}

.main-wrapper {
  padding: 1rem 0;
  width: 100%;
}

main {
  margin: 5rem auto;
}
</style>