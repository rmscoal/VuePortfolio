<script>
import About from './components/TheAbout.vue'
import Greetings from './components/Greetings.vue'

export default {
  components: {
    About,
    Greetings
  },
  data () {
    return {
      msgh1: ["Hello,", "Ola,", "Hai,"],
      msgh2: ["Welcome to my portfolio!", "Welcome to my little project!", 
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
  <header>
    <div class="wrapper">
      <Greetings :msgh1="msgh1" :msgh2="msgh2"/>
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
  display: block;
  line-height: 3rem;
  margin: 2rem auto;
}

main {
  height: inherit;
}
</style>