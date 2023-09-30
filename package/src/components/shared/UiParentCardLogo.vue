<script setup lang="ts">
import { ref } from 'vue';
import Logo from "@/layouts/full/logo/Logo.vue";
</script>

// ===============================|| Ui Parent Card||=============================== //
<template>
    <v-card elevation="10"  class="overflow-hidden">
        <v-card-item class="v-card-item bg-surface pt-4 pb-2">
            <div class="d-sm-flex align-center justify-space-between ">
                <v-card-title class="text-h5"><Logo/></v-card-title>
                <!-- <template v-slot:append> -->
                <slot name="action"></slot>
                <!-- </template> -->
            </div>
        </v-card-item>
        <v-divider></v-divider>
        <v-card-text>
            <slot />
        </v-card-text>
    </v-card>
</template>
