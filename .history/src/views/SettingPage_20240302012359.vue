<template>
    <dashboard-layout-vue title="Setting">
      <div>
        <div class="flex justify-center gap-4">
          <div class="max-w-3xl rounded-xl bg-base-300 p-8 w-full">
            <div class="flex items-center w-full justify-between">
                <div class="text-2xl">
                    Theme
                </div>
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