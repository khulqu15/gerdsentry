<template>
    <dashboard-layout-vue title="History">
      <div>
        <div class="grid md:grid-cols-2 grid-cols-1 gap-4">
          <div>
            <h1 class="text-xl font-bold mb-2">History Data</h1>
            <!-- add description -->
            <p class="text-sm mb-4">This is the history data in the system</p>            
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