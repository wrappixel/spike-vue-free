<script setup lang="ts">
import { ref } from 'vue';
import { computed } from 'vue';
import { useTheme } from 'vuetify';
const theme = useTheme();
const indigo = theme.current.value.colors.indigo;


/* Chart */
const areachartOptions = computed(() => {
    return {
        chart: {
            id: "sparkline3",
            type: "area",
            height: 60,
            sparkline: {
                enabled: true,
            },
            group: "sparklines",
            fontFamily:'inherit',
            foreColor: "#adb0bb",
        },
        series: [
            {
                name: "Earnings",
                color: "#8763da",
                data: [25, 66, 20, 40, 12, 58, 20],
            },
        ],
        stroke: {
            curve: "smooth",
            width: 2,
        },
        fill: {
            colors: ["#f3feff"],
            type: "solid",
            opacity: 0.05,
        },

        markers: {
            size: 0,
        },
        tooltip: {
            theme: "dark",
            fixed: {
                enabled: true,
                position: "right",
            },
            x: {
                show: false,
            },
        },
    };
});

const areaChart = {
    series: [
        {
            name: '',
            data: [25, 66, 20, 40, 12, 58, 20]
        }
    ]
};
</script>
<template>
    <v-card elevation="10" class="withbg">
        <v-card-item>
            <div class="d-flex align-center justify-space-between pt-sm-2">
                <v-card-title class="text-h5">Product Sales</v-card-title>
                <v-btn  size="small" icon class="bg-error">
                    <v-avatar size="20" class="text-surface">
                        <CurrencyDollarIcon size="20" />
                    </v-avatar>
                </v-btn>
            </div>
            <v-row>
                <v-col cols="12">
                    <div class="mt-2">
                        <h3 class="text-h4">$6,820</h3>
                        <div class="mt-2">
                            <v-avatar class="bg-lighterror text-accent" size="20">
                                <ArrowDownRightIcon class="text-error" size="15" />
                            </v-avatar>
                            <span class="text-subtitle-1 ml-2 font-weight-bold">+9%</span>
                            <span class="text-subtitle-1 text-muted ml-2">last year</span>
                        </div>
                    </div>
                </v-col>
            </v-row>
        </v-card-item>
        <div class="mt-3">
            <apexchart type="area" height="60" :options="areachartOptions" :series="areaChart.series"> </apexchart>
        </div>
    </v-card>
</template>
