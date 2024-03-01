<template>
    <dashboard-layout-vue title="Dashboard">
      <div>
        <div class="grid md:grid-cols-2 grid-cols-1 gap-4">
            <!-- make profile ui -->
            <div>
                <h1 class="text-xl font-bold mb-2">Profile</h1>
                <p class="text-sm mb-4">This is your profile</p>
                <div class="flex items
                -center gap-4">
                    <div class="w-20 h-20 bg-base-200 rounded-full"></div>
                    <div>
                        <h1 class="text-lg font-bold">John Doe</h1>
                        <p class="text-sm">
                            <span class="font-semibold">Email:</span>
                            <span>rizkyumar@example.com</span>
                        </p>
                        <p class="text-sm">
                            <span class="font-semibold">Phone:</span>
                            <span>081234567890</span>
                        </p>
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