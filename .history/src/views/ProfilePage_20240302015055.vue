<template>
    <dashboard-layout-vue title="Dashboard">
      <div>
        <div class="grid grid-cols-1 gap-4">
            <!-- make profile ui -->
            <div class="w-full p-8 bg-base-100">
                <div class="flex items-center gap-4">
                    <div tabindex="0" role="button" class="avatar">
                        <div class="w-24 mask mask-squircle">
                            <img src="https://daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg" />
                        </div>
                    </div>
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