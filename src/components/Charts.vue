<template>
    <div class="bg-white overflow-hidden shadow rounded-lg">
      <div class="px-4 py-5 sm:p-6">
        <h3 class="text-lg font-medium text-gray-900">{{ title }}</h3>
        <div class="mt-2">
          <LineChart :chart-data="chartData" :options="chartOptions" />
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { toRefs, defineProps } from 'vue';
  import { Line } from 'vue-chartjs';
  import { Chart as ChartJS, registerables } from 'chart.js';
  
  ChartJS.register(...registerables);
  
  const props = defineProps({
    title: {
      type: String,
      required: true,
    },
    chartData: {
      type: Object,
      required: true,
    },
    chartOptions: {
      type: Object,
      default: () => ({}),
    },
  });
  
  const { title, chartData, chartOptions } = toRefs(props);
  </script>
  
  <style scoped>
  /* Add any specific styles for ChartCard */
  </style>
  