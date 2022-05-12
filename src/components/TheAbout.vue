<script>
export default {
 data () {
   return {
     first: 'name: Rifky Manuel Satyana',
     second: 'age: ' + 22,
     third: 'nationality: Indonesian',
     fourth: 'occupation: Student',
     fifth: 'school: Gadjah Mada University',
     secondCard: false,
     centerClass: 'notCenter',
     rockerClass: 'rocker'
   }
 },
 methods: {
   nextCard () {
     if (this.secondCard == true) {
       // change values 
       this.first = 'name: Rifky Manuel Satyana'
       this.second = 'age: ' + 22,
       this.third = 'nationality: Indonesian',
       this.fourth = 'occupation: Student',
       this.fifth = 'school: Gadjah Mada University',

       this.centerClass = 'notCenter'
       this.secondCard = !this.secondCard
     } else {
       // change values 
       this.first = 'hobby: Cooking and Coding'
       this.second = 'interest: Web and Security'
       this.third = 'address: Yogyakarta'
       this.fourth = 'languages: Indonesian and English'
       this.fifth = 'That\'s all for now!'

       this.centerClass = 'center'
       this.secondCard = !this.secondCard
     }
   },
   stopRocker () {
     this.rockerClass = 'notRocker'
   }, 
   startRocker () {
     this.rockerClass = 'rocker'
   }
 }
}
</script>

<!--add vue animation box to the id card-->
<template>
  <div class="container">
    <div @mouseover="stopRocker" @mouseleave="startRocker" @mousedown.left="nextCard" :class="['box floating', rockerClass]">
      <transition name="slide" mode="out-in">
        <p :key="first"> <!--the :key triggers the animation because it changes-->
          {{ first }}
        </p>
      </transition>
      <transition name="slide" mode="out-in">
        <p :key="second">
          {{ second }}
        </p>
      </transition>
      <transition name="slide" mode="out-in">
        <p :key="third">
          {{ third }}
        </p>
      </transition>
      <transition name="slide" mode="out-in">
        <p :key="fourth">
          {{ fourth }}
        </p>
      </transition> 
      <transition name="slide" mode="out-in">
        <p :class="[centerClass]" :key="fifth">
          {{ fifth }}
        </p>
      </transition>  
    </div>
  </div>
</template>
<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono&display=swap');

.container { 
  display:flex;
  margin: 0 auto;
  justify-content: center;
}

.box{
  color:white !important;
  background: linear-gradient(155deg, #e66465, #9198e5);

  width: 400px;
  height:200px;
  padding: 1rem;
  box-shadow: 0px 5px 20px 1px;
  border-radius: .4em;
  text-align: left;
  cursor: pointer;
}

.box > p {
  font-size: 1.2em;
  font-family: 'Roboto Mono', monospace;
  margin: 0.2rem auto;
}

.box > .center {
  text-align: center;
  font-weight: 600;
}

/*  */
.box.floating{
  box-shadow:none;
}

.box.floating::after{
  content:"";
  display:block;
  width:50%;
  height:50%;
  background: aliceblue;
  position:absolute;
  bottom:15%;
  left:50%;
  transform:translateX(-50%);
  z-index:-1;
  box-shadow: 0px 5px 500px 0px;
}

.box.floating.notRocker::after {
  animation: animateRocker 10s linear 5s infinite normal paused;
}
.box.floating.rocker::after {
  animation: animateRocker 10s linear 5s infinite normal running;
}

/* Enter and leave animations can use different */
/* durations and timing functions.              */
.slide-enter-active {
  transition: all .5s ease;
}
.slide-leave-active {
  transition: all .5s cubic-bezier(.52,.22,.19,1.38);
}
.slide-enter, .slide-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}


@keyframes animateRocker {
  0% {transform:translateX(-50%)}
  10% {transform:translateX(-35%)}
  20% {transform:translateX(-65%)}
  30% {transform:translateX(-35%)}
  40% {transform:translateX(-65%)}
  50% {transform:translateX(-35%)}
  60% {transform:translateX(-65%)}
  70% {transform:translateX(-35%)}
  80% {transform:translateX(-65%)}
  90% {transform:translateX(-35%)}
  100%{transform:translateX(-50%)}
}
</style> 