<script setup>
const props = defineProps({ item: Object });
</script>

<template>
    <v-list-subheader  class="smallCap text-capitalize text-subtitle-1 mt-5 d-flex align-items-center">
        <span class="mini-icon"><DotsIcon size="16" stroke-width="1.5" class="iconClass" /></span>
       <span class="mini-text font-weight-semibold pl-2 text-medium-emphasis text-uppercase ">{{ props.item.header}}</span> 
    </v-list-subheader>
</template>
