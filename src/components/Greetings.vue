<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greeting">
    <h1>{{ msg }}</h1>
  </div>
</template>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Koulen&display=swap');

.greeting {
  margin: 2rem auto;
  text-align: center;
}
h1 {
  font-weight: 500; 
  font-size: 3rem;
  font-family: 'Koulen', cursive;
}

</style>
