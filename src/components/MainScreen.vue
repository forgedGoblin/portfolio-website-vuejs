<!-- js things -->
<script setup>
import { ref } from 'vue'

import AboutMe from './AboutMe.vue';
import Skills from './Skills.vue';
import Socials from './Socials.vue';
import Projects from './Projects.vue';
import ContactInformation from './ContactInformation.vue';
import Resume from './Resume.vue';

const tabs = ["About Me", "Skills", "Socials", "Projects", "Contact Information", "Resumé"]

const selectedTab = ref("About Me")

//tabs
const components = {
    "About Me": AboutMe,
    "Skills": Skills,
    "Socials": Socials,
    "Projects": Projects,
    "Contact Information": ContactInformation,
    "Resumé": Resume
}
</script>

<!-- html tings -->
<template>
    <div class="m-10">
        <div class="window w-100 h-100">
            <div class="title-bar">
                <div class="title-bar-text">Franco's Online Portfolio Window</div>
                    <div class="title-bar-controls">
                        <button aria-label="Help" class="bg-[#b8b8b8]"></button>
                        <button aria-label="Close" class="bg-[#b8b8b8]"></button>
                    </div>
                </div>
            <div class="window-body">
                <p>There's so much room for activities!</p>
                <br />
                <menu role="tablist">
                    <li @click="selectedTab = tab" v-for="tab in tabs" role="tab" :aria-selected="tab == selectedTab ? 'true' : 'false'"><a :href="'#' + tab.replace(' ', '_')">{{ tab }}</a></li>
                </menu>
                    <div class="window" role="tabpanel">
                        <div class="window-body">
                            <template v-if="selectedTab in components">
                                <component :is="components[selectedTab]">
                                </component>
                            </template>
                        </div>
                    </div>
            </div>
        </div>
    </div>
</template>

<!-- css tings -->
<style scoped>
    
</style>
