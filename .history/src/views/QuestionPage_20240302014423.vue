<template>
    <dashboard-layout-vue title="Question">
      <div>
        <div class="grid grid-cols-1 gap-4">
            <!-- make quisionaire question using checkbox, radio, and textare -->
            <div>
                <h1 class="text-xl font-bold mb-2">Quisionaire</h1>
                <p class="text-sm mb 4">Please fill the quisionaire</p>
            </div>
            <div class="w-full p-4 bg-base-100 rounded-xl">
                <!-- question content about user healthy -->
                <div v-for="(item, index) in question_data" :key="index">
                    <div class="form_control">
                        <label class="text">{{ item.question }}</label>
                        <div v-if="item.type == 'radio'">
                            <div v-for="(option, index) in item.options" :key="index">
                                <input type="radio" :value="option.value" v-model="item.value" class="radio">
                                <label>{{ option.label }}</label>
                            </div>
                        </div>
                        <div v-else-if="item.type == 'checkbox'">
                            <div v-for="(option, index) in item.options" :key="index">
                                <input type="checkbox" :value="option.value" v-model="item.value" class="checkbox">
                                <label>{{ option.label }}</label>
                            </div>
                        </div>
                        <div v-else-if="item.type == 'textarea'">
                            <textarea v-model="item.value" class="textarea input input-bordered w-full text-base-content bg-base-200/30"></textarea>
                        </div>
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
  const question_data = ref([
    {
        question: 'Apakah anda merasa sehat?',
        type: 'radio',
        options: [
            {
                value: 'Ya',
                label: 'Ya'
            },
            {
                value: 'Tidak',
                label: 'Tidak'
            }
        ],
        value: [],
    }, // add question using checkbox
    {
        question: 'Apakah anda merasa demam?',
        type: 'checkbox',
        options: [
            {
                value: 'Ya',
                label: 'Ya'
            },
            {
                value: 'Tidak',
                label: 'Tidak'
            }
        ],
        value: [],
    }, // add question using textarea
    {
        question: 'Apakah anda merasa sesak nafas?',
        type: 'textarea',
        value: []
    }
  ])
  </script>