<script>
/* import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    setup() {
        
    },
}) */

export default {
    mounted () {
        console.log('NavGuide is mounted!')
    }
}
</script>

<template>
    <div class="sidebar">
        <div class="nav">
            <a href="#greeting">Card</a>
            <a>Skills</a>
        </div>
    </div>
</template>

<style scoped>

.sidebar {
 position: fixed;
 float: right;
 display: flex;
 flex-direction: column;
 justify-content: center;
 overflow-x: hidden;
 overflow-y: auto;
 padding: 0.5rem;
 height: 100%;
 min-width: 5%;
 max-width: 10%;
 z-index: 2;
}

.sidebar > .nav {
 display:flex;
 flex-direction: column;
 text-align: center;
 justify-content: center;
 background-color: var(--vt-c-divider-dark-2);
 min-height:15%;
 border-radius: 2rem;
 padding: 0.5em;
}

.nav > a {
    text-decoration: none;
    color: var(--color-text);
    cursor: pointer;
    border-radius: 0.8rem;
    padding: 0.3rem;
    transition: background-color 0.2s ease-out, font-weight 0.5s;

}

.nav > a:hover {
    color:white !important;
    font-weight:500;
    background-color: #e86601; 
    scale: 1.1;
}
</style>