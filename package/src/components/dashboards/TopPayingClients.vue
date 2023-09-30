<script setup lang="ts">
import { ref } from 'vue';
import {productPerformance} from '@/data/dashboard/dashboardData';
const items = ref([
    { title: "Action" },
    { title: "Another action" },
    { title: "Something else here" },
]);
</script>
<template>
    <v-card elevation="10" class="pb-2">
        <v-card-item class="pa-6">
            <div class="d-flex align-center justify-space-between">
                <div>
                    <h5 class="text-h5 mb-1 font-weight-semibold">Top Paying Clients</h5>
                </div>
                <div>
                    <v-menu bottom left>
                        <template v-slot:activator="{ props }">
                            <v-btn icon color="inherit" v-bind="props" flat>
                                <DotsVerticalIcon stroke-width="1.5" size="24" class="text-grey100" />
                            </v-btn>
                        </template>
                        <v-list density="compact">
                            <v-list-item v-for="(item, i) in items" :key="i" :value="i">
                                <v-list-item-title>{{ item.title }}</v-list-item-title>
                            </v-list-item>
                        </v-list>
                    </v-menu>
                </div>
            </div>
        <v-table class="month-table">
            <thead>
                <tr>
                    <th class="text-subtitle-1 font-weight-bold">Id</th>
                    <th class="text-subtitle-1 font-weight-bold">Assigned</th>
                    <th class="text-subtitle-1 font-weight-bold">Name</th>
                    <th class="text-subtitle-1 font-weight-bold">Priority</th>
                    <th class="text-subtitle-1 font-weight-bold text-right">Budget</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in productPerformance" :key="item.name" class="month-item">
                    <td>
                        <p class="text-15 font-weight-medium">{{ item.id }}</p>
                    </td>
                    <td>
                        <div class="">
                                <h6 class="text-subtitle-1 font-weight-bold">{{ item.name }}</h6>
                                <div class="text-subtitle-2 mt-1 text-muted">{{ item.post }}</div>
                        </div>
                    </td>
                    <td>
                        <h6 class="text-body-1 text-muted">{{ item.pname }}</h6>
                    </td>
                    <td>
                        <v-chip  :class="'text-body-2 bg-' + item.statuscolor " color="white"  size="small" >{{
                            item.status
                        }}</v-chip>
                    </td>
                    <td>
                        <h6 class="text-h6 text-right">{{ item.budget }}</h6>
                    </td>
                </tr>
            </tbody>
        </v-table>
        </v-card-item>
    </v-card>
</template>
