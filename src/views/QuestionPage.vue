<template>
    <dashboard-layout-vue title="Question">
      <div>
        <div class="grid grid-cols-1 gap-4">
            <!-- make quisionaire question using checkbox, radio, and textare -->
            <div>
                <h1 class="text-xl font-bold mb-2">Quisionaire</h1>
                <p class="text-sm mb 4">Please fill the quisionaire</p>
            </div>
            <div class="w-full p-4 bg-base-100 rounded-xl space-y-4">
                <form @click="onSubmit($event)">
                    <div v-for="(item, index) in question_data" :key="index">
                        <div class="form_control">
                            <p class="text font-semibold inline-block mb-4">{{ index + 1 }}. {{ item.question }}</p>
                            <div v-if="item.type == 'radio'">
                                <div v-for="(option, idx) in item.options" :key="idx" class="flex items-center gap-x-2 mb-2">
                                    <input type="radio" :required="index == 0 ? 'true' : 'false'" :name="`radio-${index}`" :value="option.value" v-model="item.value" class="radio">
                                    <label>{{ option.label }}</label>
                                </div>
                            </div>
                            <div v-else-if="item.type == 'checkbox'">
                                <div v-for="(option, idx) in item.options" :key="idx" class="flex items-center gap-x-2 mb-2">
                                    <input type="checkbox" required :name="`checkbox-${idx}`" :value="option.value" v-model="item.value" class="checkbox">
                                    <label>{{ option.label }}</label>
                                </div>
                            </div>
                            <div v-else-if="item.type == 'textarea'">
                                <textarea v-model="item.value" :name="`textarea-${index}`" required class="textarea input input-bordered w-full text-base-content bg-base-200/30"></textarea>
                            </div>
                        </div>
                    </div>
                    <!-- add checkbout button for seriously submit -->
                    <div class="flex items-center my-8 gap-3">
                        <input type="checkbox" required class="checkbox">
                        <label class="text-sm">I'm seriously to submit this quisionaire</label>
                    </div>
                    <button class="btn btn-primary text-white">Submit</button>
                </form>
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
  
  function onSubmit(event: Event) {
    router.push({name: 'Question'})
  }

  const router = useRouter()
  const question_data = ref([
    {
        question: 'Seberapa sering Anda mengalami perasaan terbakar di bagian belakang tulang Anda ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    }, // add question using checkbox
    {
        question: 'Seberapa sering Anda mengalami naiknya isi lambung ke arah tenggorokan atau mulut (regurgitasi) ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    },
    {
        question: 'Seberapa sering Anda mengalami nyeri ulu hati ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    },
    {
        question: 'Seberapa sering Anda mengalami mual ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    },
    {
        question: 'Seberapa sering Anda mengalami kesulitan tidur malam oleh karena rasa terbakar di dada atau naiknya isi perut ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    },
    {
        question: 'Seberapa sering Anda meminum obat tambahan untuk rasa terbakar di dada dan / naiknya isi perut, selain yang diberikan oleh dokter Anda (seperti obat maag yang dijual bebas) ?',
        type: 'radio',
        options: [
            {
                value: '0',
                label: '0 hari'
            },
            {
                value: '1',
                label: '1 hari'
            },
            {
                value: '2',
                label: '2-3 hari'
            },
            {
                value: '3',
                label: '4-7 hari'
            },
        ],
        value: [],
    }, 
    {
        question: "Menurunkan berat badan bila penderita obesitas atau menjaga berat badan sesuai dengan IMT ideal ?",
        type: 'radio',
        options: [
            {
                value: '0',
                label: 'Tidak pernah'
            }, 
            {
                value: '1',
                label: 'Ya, Pernah'
            }
        ],
        value: [],
    },
    {
        question: "Meninggikan kepala ± 15-20 cm/ menjaga kepala agar tetap elevasi saat posisi berbaring ?",
        type: 'radio',
        options: [
            {
                value: '0',
                label: 'Tidak pernah'
            }, 
            {
                value: '1',
                label: 'Ya, Pernah'
            }
        ],
        value: [],
    },
    {
        question: "Makan malam paling lambat 2 – 3 jam sebelum tidur ?",
        type: 'radio',
        options: [
            {
                value: '0',
                label: 'Tidak pernah'
            }, 
            {
                value: '1',
                label: 'Ya, Pernah'
            }
        ],
        value: [],
    },
    {
        question: "Menghindari makanan yang dapat merangsang GERD seperti cokelat, minuman mengandung kafein, alkohol, dan makanan berlemak - asam - pedas ?",
        type: 'radio',
        options: [
            {
                value: '0',
                label: 'Tidak pernah'
            }, 
            {
                value: '1',
                label: 'Ya'
            }
        ],
        value: [],
    },
    
    // add question using textarea
    
    // {
    //     question: 'Apakah Anda merasa demam?',
    //     type: 'checkbox',
    //     options: [
    //         {
    //             value: 'Ya',
    //             label: 'Ya'
    //         },
    //         {
    //             value: 'Tidak',
    //             label: 'Tidak'
    //         }
    //     ],
    //     value: [],
    // }, // add question using textarea
    // {
    //     question: 'Apakah Anda merasa sesak nafas?',
    //     type: 'textarea',
    //     value: []
    // }
  ])
  </script>