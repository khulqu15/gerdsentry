<template>
  <dashboard-layout-vue title="Dashboard">
    <div>
      <div class="grid md:grid-cols-2 grid-cols-1">
        <div class="grid grid-cols-2 gap-3">
          <div class="w-full p-3 bg-primary rounded-xl" v-for="(item, index) in count_datas" :key="index">
            <div class="text-white text-sm font-bold">{{ item.title }}</div>
            <div class="text-white text-3xl font-bold">{{ item.value }}</div>
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
const count_datas = ref([
  {
    title: 'Data Historis',
    value: 0
  },
  {
    title: 'Data User',
    value: 0
  },
  {
    title: 'Data Responden Kuisioner',
    value: 0
  },
  {
    title: 'Data Kadar Oksigen',
    value: 0
  },
  {
    title: 'Data Kadar Karbon Dioksida',
    value: 0
  },
  {
    title: 'Data Kadar Amonia',
    value: 0
  }
])
</script>