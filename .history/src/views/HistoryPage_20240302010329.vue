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
                        <button class="btn btn-primary">Export Data</button>
                    </div>
                </div>
            </div>
            <div class="w-full">
                <!-- add btn join to view menu for chart and table -->
                <div class="joins">
                    <button class="btn btn-primary">Chart</button>
                    <button class="btn btn-primary">Table</button>
                </div>
            </div>
        </div>
      </div>
    </dashboard-layout-vue>
  </template>
  
  <script setup lang="ts">
  import DashboardLayoutVue from '@/layouts/DashboardLayout.vue'
  import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue'
  import { onMounted, ref } from 'vue'
  import { useRouter } from 'vue-router'
  
  const router = useRouter()
  </script>