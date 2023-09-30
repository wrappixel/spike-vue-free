<script setup lang="ts">
import { RouterView } from 'vue-router';
import MainView from './Main.vue';
</script>

<template>
    <v-locale-provider >
        <v-app>
            <MainView />
            <v-main>
                <v-container fluid class="page-wrapper bg-background px-sm-5 px-4  pt-12 rounded-xl">
                    <div class="maxWidth">
                        <RouterView />
                    </div>
                </v-container>
            </v-main>
        </v-app>
    </v-locale-provider>
</template>
