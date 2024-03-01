<template>
  <dashboard-layout-vue title="Dashboard">
    <div>
      <div class="grid md:grid-cols-2 grid-cols-1 gap-4">
        <div>
          <div class="grid grid-cols-2 gap-3">
            <div class="w-full p-3 bg-primary rounded-xl" v-for="(item, index) in count_datas" :key="index">
              <div class="text-white text-sm font-bold">{{ item.title }}</div>
              <div class="text-white text-3xl font-bold">{{ item.value }}</div>
            </div>
          </div>
        </div>
        <div>
          <div class="w-full bg-base-100 p-4 rounded-xl">
            <form>
              <!-- form name, birthday, address for start quisionaire -->
              <!-- add title -->
              <div class="text-xl font-bold">Start Quisionaire</div>
              <!-- add description -->
              <p class="text-sm mt-1 mb-4">Please fill the form below to start quisionaire</p>
              <div class="grid grid-cols-2 items-center gap-3">
                <div class="form_control">
                  <label for="name" class="text-sm">Name</label>
                  <input id="name" type="text" required placeholder="Enter your name here" class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
                <div class="form_control">
                  <label for="birthday" class="text-sm">Birthday</label>
                  <input id="birthday" type="date" required class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
              </div>
              <div class="form_control mt-3">
                <label for="address" class="text-sm">Address</label>
                <input id="address" type="text" required placeholder="Enter your address here" class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
              </div> 
              <button type="submit" class="btn btn-primary w-full mt-3 text-white">Start Quisionaire</button>
            </form>
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