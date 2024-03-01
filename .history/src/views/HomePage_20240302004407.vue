<template>
  <dashboard-layout-vue title="Dashboard">
    <div>
      <div class="grid md:grid-cols-2 grid-cols-1">
        <div class="grid grid-cols-2 gap-3">
          <div class="w-full p-3 bg-primary" v-for="(item, index) in count_datas" :key="index"></div>
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
const count_datas = ref([
  {
    title: 'Data Suhu',
    value: 0
  },
  {
    title: 'Data Kelembapan',
    value: 0
  },
  {
    title: 'Data Tekanan',
    value: 0
  },
  {
    title: 'Data Kadar Oksigen',
    value: 0
  }
])
</script>