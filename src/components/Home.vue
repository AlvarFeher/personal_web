<template>
    <div id="app">
        <div class="parent-container" style="display: flex; flex-direction: column;">
            <v-container class="titleBar" fluid style="background-color: #7dcfb6; display: flex; flex-direction: row;">
                <v-btn-group>
                    <v-btn @click="onClick('.experience')">Experience</v-btn>
                    <v-btn @click="onClick('.education')">Education</v-btn>
                    <v-btn @click="onClick('.aboutme')">About me</v-btn>
                    <v-btn @click="onClick('.projects')">Projects</v-btn>
                </v-btn-group>
            </v-container>
            <div class="sections" fluid>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="himynameis">
                    <Section1 />
                </div>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="currently" id="currently" style="margin-bottom: 200px;">
                    <Section2 />
                </div>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="experience" id="experience" style="margin-bottom: 200px;">
                    <Section3 />
                </div>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="education" id="education" style="margin-bottom: 200px;">
                    <v-card height="100">
                        education
                    </v-card>
                </div>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="aboutme" id="aboutme" style="margin-bottom: 200px;">
                    <v-card height="100">
                        about me
                    </v-card>
                </div>
                <v-divider :thickness="8" class="border-opacity-100"></v-divider>
                <div class="projects" id="projects">
                    <v-card height="100">
                        projects
                    </v-card>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import { computed, ref } from 'vue'
import { useGoTo } from 'vuetify'

import Section1 from '@/components/HiMyNameIs.vue';
import Section2 from '@/components/Currently.vue';
import Section3 from '@/components/Experience.vue';

export default {
    components: {
        Section1, Section2, Section3
    },
    setup() {
        const goTo = useGoTo();

        const options = computed(() => ({
            duration: 300,
            easing: 'linear',
            offset: 0,
        }))
        return { goTo, options }
    },
    data: () => ({
        items: [
            { title: 'Linked In' },
            { title: 'Git Hub' },
            { title: 'email' },
        ]
    }),
    methods: {
        onClick(sectionId) {
            //this.goTo('.experience', this.options.value)

            this.goTo(sectionId, this.options.value);
        }
    }
}

</script>

