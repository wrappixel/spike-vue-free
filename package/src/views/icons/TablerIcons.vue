<script setup lang="ts">
import { ref } from 'vue';
import UiParentCard from '@/components/shared/UiParentCard.vue';
// theme breadcrumb
const page = ref({ title: 'Tabler Icons' });
const breadcrumbs = ref([
    {
        text: 'Home',
        disabled: false,
        href: '#'
    },
    {
        text: 'Tabler icons',
        disabled: true,
        href: '#'
    }
]);
</script>
<template>
    <v-row>
        <v-col cols="12" md="12">
            <v-card elevation="10">
                <v-card-text class="pa-5"> 
                <div class="pa-7 pt-0">
                    <iframe src="https://tabler-icons.io/" title="Inline Frame Example" frameborder="0" width="100%" height="650"></iframe>
                </div>
            </v-card-text>
            </v-card>
        </v-col>
    </v-row>
</template>
