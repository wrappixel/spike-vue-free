<script setup>
const props = defineProps({ item: Object, level: Number });
</script>

<template>
    <div class="mb-0">
        <!---Single Item-->
        <v-list-item
            :href="item.external ? item.to : undefined"
            :to="!item.external ? item.to : undefined"
            rounded="lg"
            class=""
            color=""
            :ripple="false"
            :disabled="item.disabled"
           :target="item.external === true ? '_blank' : undefined"
            v-scroll-to="{ el: '#top' }"
        >
            <!---If icon-->
            <template v-slot:prepend>
                <div class="sublink-dot ml-4"></div>
            </template>
            <v-list-item-title class="ml-4 text-body-1">{{ item.title }}</v-list-item-title>
            <!---If Caption-->
            <v-list-item-subtitle v-if="item.subCaption" class="text-caption mt-n1 hide-menu">
                {{ item.subCaption }}
            </v-list-item-subtitle>

            <!---If any chip or label-->
            <template v-slot:append v-if="item.chip">
                <v-chip
                    color="primary"
                    class="sidebarchip hide-menu"
                    :size="item.chipIcon ? 'x-small' : 'x-small'"
                    :variant="item.chipVariant"
                    :prepend-icon="item.chipIcon"
                >
                    {{ item.chip }}
                </v-chip>
            </template>
        </v-list-item>
    </div>
</template>
