<template>
    <v-container class="titleBar" fluid style="background-color: #7dcfb6;">
        <v-menu>
            <template v-slot:activator="{ props }">
                <v-btn v-bind="props" flat position="absolute" top="0" left="0" style="font-size: xx-large;"> Hi, My name is
                    Álvaro Feher...</v-btn>
            </template>
            <v-list>
                <v-list-item v-for="(item, i) in items" :key="i">
                    <v-btn>{{ item.title }}</v-btn>
                </v-list-item>
            </v-list>
        </v-menu>
    </v-container>
    <v-container class="sections" fluid>
        <v-divider :thickness="8" class="border-opacity-100"></v-divider>
        <div class="currently">
            <v-card height="800" width="100%">
                Currently
            </v-card>
        </div>
        <v-divider :thickness="8" class="border-opacity-100"></v-divider>
        <div class="experience">
            <v-card height="100">
                experience
            </v-card>
        </div>
        <v-divider :thickness="8" class="border-opacity-100"></v-divider>
        <div class="education">
            <v-card height="100">
                education
            </v-card>
        </div>
        <v-divider :thickness="8" class="border-opacity-100"></v-divider>
        <div class="about me">
            <v-card height="100">
                about me
            </v-card>
        </div>
        <v-divider :thickness="8" class="border-opacity-100"></v-divider>
        <div class="projects">
            <v-card height="100">
                projects
            </v-card>
        </div>
    </v-container>
</template>

<script>
export default {
    data: () => ({
        items: [
            { title: 'Linked In' },
            { title: 'Git Hub' },
            { title: 'email' },
        ]
    }),
}
</script>

