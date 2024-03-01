<template>
    <dashboard-layout-vue title="History">
      <div>
        <div class="grid px-8 grid-cols-1 gap-4">
            <div>
                <div class="flex items-center justify-between">
                    <div>
                        <h1 class="text-xl font-bold mb-2">History Data</h1>
                        <p class="text-sm mb-4">This is the history data in the system</p>
                    </div>
                    <div>
                        <button @click="exportData()" class="btn btn-primary">Export Data</button>
                    </div>
                </div>
            </div>
            <div class="w-full">
                <!-- add btn join to view menu for chart and table -->
                <div class="join">
                    <button @click="view_type = 'table'" :class="{'btn-primary': view_type == 'table'}" class="btn join-item">Table</button>
                    <button @click="view_type = 'chart'" :class="{'btn-primary': view_type == 'chart'}" class="btn join-item">Chart</button>
                </div>
            </div>
            <div class="w-full" v-if="view_type == 'table'">
                <table class="table table-compact">
                    <thead>
                        <tr>
                            <th>Timestamp</th>
                            <th>Temperature</th>
                            <th>Humidity</th>
                            <th>CO2</th>
                            <th>TVOC</th>
                            <th>Name</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(item, index) in data_table" :key="index">
                            <td>{{ item.timestamp }}</td>
                            <td>{{ item.temperature }}</td>
                            <td>{{ item.humidity }}</td>
                            <td>{{ item.co2 }}</td>
                            <td>{{ item.tvoc }}</td>
                            <td>{{ item.name }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div v-else class="w-full">
                <Line :data="data_chart" :options="option_chart"></Line>
            </div>
        </div>
      </div>
    </dashboard-layout-vue>
  </template>
  
  <script setup lang="ts">
  import DashboardLayoutVue from '@/layouts/DashboardLayout.vue'
  import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue'
  import { onMounted, ref } from 'vue'
  import {
    Chart as ChartJS,
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend
  } from 'chart.js'
  import { Line } from 'vue-chartjs'
  import { useRouter } from 'vue-router'
  
  const router = useRouter()
  const view_type = ref('table')

  ChartJS.register(
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend
  )

  const data_chart = ref({
    labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
    datasets: [
        {
            label: 'Temperature',
            data: [65, 59, 80, 81, 56, 55, 40],
            borderColor: 'rgb(75, 192, 192)',
            tension: 0.1
        },
        {
            label: 'Humidity',
            data: [28, 48, 40, 19, 86, 27, 90],
            borderColor: 'rgb(255, 99, 132)',
            tension: 0.1
        },
        {
            label: 'CO2',
            data: [28, 48, 40, 19, 86, 27, 90],
            borderColor: 'rgb(255, 205, 86)',
            tension: 0.1
        },
        {
            label: 'TVOC',
            data: [28, 48, 40, 19, 86, 27, 90],
            borderColor: 'rgb(54, 162, 235)',
            tension: 0.1
        }
    ]
  })

  const option_chart = ref({
    responsive: true,
    maintainAspectRatio: false,
    scales: {
        y: {
            beginAtZero: true
        }
    }
  })

  const data_table = ref([
    {
        timestamp: '2021-10-10 10:00:00',
        temperature: 36.5,
        humidity: 60,
        co2: 500,
        tvoc: 100,
        name: 'Rizky Umar Salim',
    },
    // generate 10 data with unique timestamp and name
    ...Array.from({length: 10}, (v, k) => k).map((item, index) => {
        return {
            timestamp: `2021-10-10 10:0${index}:00`,
            temperature: 36.5 + index,
            humidity: 60 + index,
            co2: 500 + index,
            tvoc: 100 + index,
            name: `Rizky Umar Salim ${index}`,
        }
    })
  ])

  function exportData() {
    // make export data to csv file
    const csv = data_table.value.map(row => Object.values(row).join(',')).join('\n');
    const blob = new Blob([csv], { type: 'text/csv' });
    const url = window.URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.setAttribute('hidden', '');
    a.setAttribute('href', url);
    a.setAttribute('download', 'data.csv');
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);

  }
  </script>