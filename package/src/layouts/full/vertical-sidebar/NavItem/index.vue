<script setup>
import { Icon } from '@iconify/vue';
const props = defineProps({ item: Object, level: Number });
</script>

<template>
    <!---Single Item-->
    <div class="mb-1">
        <v-list-item
            :href="item.external ? item.to : undefined"
            :to="!item.external ? item.to : undefined"
            class="bg-hover-primary"
            color="primary"
            :ripple="false"
            :disabled="item.disabled"
            :target="item.external === true ? '_blank' : undefined"
        >
            <!---If icon-->
            <template v-slot:prepend>
                <div class="navbox bg-hover-primary">
                    <span class="icon-box">
                        <Icon :icon="'solar:' + item.icon" height="24" width="24" :level="level" :class="'position-relative z-index-2 '" />
                    </span>
                </div>
            </template>

            <v-list-item-title class="text-subtitle-1 font-weight-medium" color="primary"
                >{{ item.title }}

                <span v-if="item.children">
                    <span v-if="item.chip" class="ps-3">
                        <v-chip color="primary" class="sidebarchip hide-menu bg-lightprimary" size="x-small">
                            {{ item.chip }}
                        </v-chip>
                    </span>
                </span>
            </v-list-item-title>
            <!---If Caption-->
            <v-list-item-subtitle v-if="item.subCaption" class="text-caption mt-n1 hide-menu">
                {{ item.subCaption }}
            </v-list-item-subtitle>
            <!---If any chip or label-->
            <template v-slot:append v-if="item.chip">
                <v-chip color="primary" class="sidebarchip hide-menu" size="x-small">
                    {{ item.chip }}
                </v-chip>
            </template>
        </v-list-item>
    </div>
</template>
