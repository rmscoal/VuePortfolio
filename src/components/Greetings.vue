<script>
/* defineProps({
  msg: {
    type: String,
    required: true
  }
}) */

export default {
  props: {
    msgh1: {
      type: Array,
      required: true
    },
    msgh2: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      n: 0,
      m: 0
    }
  },
  methods: {

  },
  mounted () {
    setInterval(() => {
      this.n = (this.n + 1) % this.msgh1.length;
      this.m = (this.m + 1) % this.msgh2.length;
    }, 5000)
  },
  created () {

  }
}
</script>

<template>
  <header>
    <div class="greeting">
      <!-- Make new wrapper for h1 and h2 such that can position: absolute -->
      <div class="greeting wrapper">
        <transition name="slide-up">
          <h1 :key="n">{{msgh1[n]}}</h1>  
        </transition> 
      </div>
      <div class="greeting wrapper">
        <transition>
        <h2 :key="m">{{ msgh2[m] }}</h2>
        </transition>
      </div>
    </div>
  </header>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Koulen&display=swap');

header {
  display: block;
  line-height: 3rem;
  margin: 2rem auto;
}

.greeting {
  margin: 0 auto;
  display: block;
}
.greeting.wrapper > h1 {
  position: absolute;
  font-weight: 500; 
  font-size: 3rem;
  font-family: 'Koulen', cursive;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
}

.greeting.wrapper > h2 {
  position: absolute;
  font-weight: 300; 
  font-size: 2.5rem;
  font-family: 'Koulen', cursive;
  margin: 0 auto;
  left: 0;
  right: 0;
}

.greeting.wrapper {
  width: 100%;
  min-height: 3rem;
  margin: 0.5rem auto;
  padding: 0.5rem auto;
  text-align: center;
}

/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease-out;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.slide-up-enter-active,
.slide-up-leave-active {
  transition: all 0.25s ease-out;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateY(30px);
}

.slide-up-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}
</style>
