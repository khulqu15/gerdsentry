<template>
  <dashboard-layout-vue title="Dashboard">
    <div>
      <div class="grid md:grid-cols-2 grid-cols-1">
        <div class="grid grid-cols-2">
          <div></div>
        </div>
      </div>
    </div>
  </dashboard-layout-vue>
</template>

<script setup lang="ts">
import DashboardLayoutVue from '@/layouts/DashboardLayout.vue';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
</script>