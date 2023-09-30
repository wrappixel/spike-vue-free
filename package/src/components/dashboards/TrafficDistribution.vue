<script setup lang="ts">
import { computed } from 'vue';
import { useTheme } from 'vuetify';
const theme = useTheme();
const primary = theme.current.value.colors.primary;
const lightprimary = theme.current.value.colors.lightprimary;
const chartOptions = computed(() => {
    return {
        series: [5368, 3500, 4106],
        labels: ["5368", "Refferal Traffic", "Oragnic Traffic"],
        chart: {
            height: 170,
            type: "donut",
            fontFamily: "Plus Jakarta Sans', sans-serif",
            foreColor: "#c6d1e9",
        },

        tooltip: {
            theme: "dark",
            fillSeriesColor: false,
        },

        colors: ["#e7ecf0", "#fb977d", primary],
        dataLabels: {
            enabled: false,
        },

        legend: {
            show: false,
        },

        stroke: {
            show: false,
        },
        responsive: [
            {
                breakpoint: 991,
                options: {
                    chart: {
                        width: 150,
                    },
                },
            },
        ],
        plotOptions: {
            pie: {
                donut: {
                    size: '80%',
                    background: "none",
                    labels: {
                        show: true,
                        name: {
                            show: true,
                            fontSize: "12px",
                            color: undefined,
                            offsetY: 5,
                        },
                        value: {
                            show: false,
                            color: "#98aab4",
                        },
                    },
                },
            },
        },

    };
});
const Chart = [38, 40, 25];
</script>
<template>
    <v-card elevation="10" class="withbg">
        <v-card-item>
            <div class="d-sm-flex align-center justify-space-between pt-sm-2">
                <v-card-title class="text-h5">Traffic Distribution</v-card-title>
            </div>
            <v-row>
                <v-col cols="6" sm="7">
                    <div class="mt-6">
                        <h3 class="text-h4">$36,358</h3>
                        <div class="mt-2">
                            <v-avatar class="bg-lightsuccess text-success" size="20">
                                <ArrowUpLeftIcon size="15" />
                            </v-avatar>
                            <span class="text-subtitle-2 ml-2 font-weight-bold">+9%</span>
                            <span class="text-subtitle-2 text-muted ml-2">last year</span>
                        </div>
                        <div class="d-flex align-center mt-4 ml-1">
                            <h6 class="text-subtitle-2 text-muted">
                                <v-icon icon="mdi mdi-checkbox-blank-circle" class="mr-1" size="10"
                                    color="primary"></v-icon> Oragnic
                            </h6>
                            <h6 class="text-subtitle-2 text-muted pl-5">
                                <v-icon icon="mdi mdi-checkbox-blank-circle" class="mr-1" size="10" color="error"></v-icon>
                                Refferal
                            </h6>
                        </div>
                    </div>
                </v-col>
                <v-col cols="6" sm="5" class="pl-lg-0">
                    <div class="d-flex align-center flex-shrink-0">
                        <apexchart type="donut" height="170" :options="chartOptions" :series="Chart">
                        </apexchart>
                    </div>
                </v-col>
            </v-row>
        </v-card-item>
    </v-card>
</template>