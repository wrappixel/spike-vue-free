<script setup>
import Icon from '../Icon.vue';
const props = defineProps({ item: Object, level: Number });
</script>

<template>
    <!---Single Item-->
    <div class="mb-1">
        <v-list-item  :to="item.type === 'external' ? '' : item.to" :href="item.type === 'external' ? item.to : ''" rounded
            :class="'  bg-hover-' + item.BgColor" :color="item.BgColor" :ripple="false" :disabled="item.disabled"
            :target="item.type === 'external' ? '_blank' : ''">
            <!---If icon-->
            <template v-slot:prepend>
                <div :class="'navbox  bg-hover-' + item.BgColor" :color="item.BgColor">
                    <span class="icon-box">
                        <Icon :item="item.icon" :level="level" :class="'position-relative z-index-2 texthover-' + item.BgColor" />
                    </span>
                </div>
            </template>
            <v-list-item-title class="text-subtitle-1 font-weight-medium" :color="item.BgColor">{{ item.title}}</v-list-item-title>
            <!---If Caption-->
            <v-list-item-subtitle v-if="item.subCaption" class="text-caption mt-n1 hide-menu">
                {{ item.subCaption }}
            </v-list-item-subtitle>
            <!---If any chip or label-->
            <template v-slot:append v-if="item.chip">
                <v-chip :color="item.chipColor" class="sidebarchip hide-menu"
                    :size="item.chipIcon ? 'x-small' : 'x-small'" :variant="item.chipVariant" :prepend-icon="item.chipIcon">
                    {{ item.chip }}
                </v-chip>
            </template>
        </v-list-item>
    </div>
</template>
