<script>
// 3D Corusel
import IconHolder from './icons/IconHolder.vue'
import JavaScriptIcon from './icons/JavaScriptIcon.vue'

export default {
    components: {
        IconHolder,
        JavaScriptIcon
    }
}
</script>

<template>
<div class="skills">
    <IconHolder>
        <JavaScriptIcon />
    </IconHolder>
    <IconHolder>
        <!-- Make Vue Icon -->
        <JavaScriptIcon /> 
    </IconHolder>
</div>
</template>

<style scoped>
.skills {
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    height: auto;
    margin: 5rem auto;
    padding: 1rem;
}
</style> 
