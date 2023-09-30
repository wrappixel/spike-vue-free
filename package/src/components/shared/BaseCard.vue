<script setup lang="ts">
const props = defineProps({
  heading: String,
});
</script>

<template>
  <v-card class="overflow-hidden"  elevation="10">
    <v-toolbar color="transparent">
        <v-card-title class="text-h5">{{ heading }}</v-card-title>

      <v-spacer></v-spacer>
    </v-toolbar>
    <v-divider></v-divider>
    <div class="pa-5">
      <slot />
    </div>
  </v-card>
</template>