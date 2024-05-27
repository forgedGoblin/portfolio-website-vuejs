<script setup>
import { ref } from 'vue';

const name = ref("Franco");
const greet = ref("Hello");
const occupation = ref("front-end developer");

</script>

<template>
    <div>
        <h1 class="text-2xl">About Me</h1>
        <br />
        <p class="text-base">
            {{ greet }}, my name is {{ name }}, and I am a <span v-text="occupation"></span> with a passion for creating beautiful and functional websites. I have experience with a variety of technologies including HTML, CSS, JavaScript, Vue.js, Node.js, and MongoDB. I am always looking to learn new things and improve my skills.
        </p>
    </div>
</template>

<style scoped>

</style>