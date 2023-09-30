<script setup lang="ts">
import { ref } from 'vue';
import { computed } from 'vue';
import { useTheme } from 'vuetify';
import { DotsVerticalIcon } from 'vue-tabler-icons';
const items = ref([
    { title: "Action" },
    { title: "Another action" },
    { title: "Something else here" },
]);

const theme = useTheme();
const primary = theme.current.value.colors.primary;
const error = theme.current.value.colors.error;
const chartOptions = computed(() => {
    return {

        series: [
            {
                name: "Pixel ",
                data: [9, 5, 3, 7, 5, 10, 3],
            },
            {
                name: "Ample ",
                data: [6, 3, 9, 5, 4, 6, 4],
            },
        ],
        chartOptions: {
            grid: {
                borderColor: 'rgba(0,0,0,0.1)',
                strokeDashArray: 3,
                xaxis: {
                    lines: {
                        show: false
                    }
                },
                
            },
            plotOptions: {
                bar: { horizontal: false, columnWidth: "35%", borderRadius: [8] },
            },
            colors: [primary, error],
            chart: {
                fontFamily: 'inherit',
                type: "bar",
                height: 360,
                offsetY: 10,
                toolbar: {
                    show: false,
                },
            },
            dataLabels: {
                enabled: false,
            },
            stroke: {
                show: true,
                width: 5,
                colors: ["transparent"],
            },
            xaxis: {
                type: "category",
                categories: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
                axisTicks: {
                    show: false,
                },
                axisBorder: {
                    show: false,
                },
                labels: {
                    style: {
                        colors: "#a1aab2",
                    },
                },
            },
            yaxis: {
                labels: {
                    style: {
                        colors: "#a1aab2",
                    },
                },
            },
            fill: {
                opacity: 1,
                colors: [primary, error],
            },
            tooltip: {
                theme: "dark",
            },
            legend: {
                show: false,
            },
            responsive: [
                {
                    breakpoint: 767,
                    options: {
                        stroke: {
                            show: false,
                            width: 5,
                            colors: ["transparent"],
                        },
                    },
                },
            ],

        },
    };
});
</script>
<template>
    <v-card elevation="10">
        <v-card-item>
            <div class="d-flex align-center justify-space-between">
                <div>
                    <h5 class="text-h5 mb-1 font-weight-semibold">Profit & Expenses</h5>
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

            <v-row>
                <v-col cols="12" class="pt-7">
                    <apexchart type="bar" height="370px" :options="chartOptions.chartOptions" :series="chartOptions.series">
                    </apexchart>
                </v-col>
            </v-row>
        </v-card-item>
    </v-card>
</template>
<!-- 
<style type="text/css">
.profit-expense .apexcharts-bar-series.apexcharts-plot-series .apexcharts-series path {
    clip-path: inset(0 0 5% 0 round 20px);
}
</style> -->