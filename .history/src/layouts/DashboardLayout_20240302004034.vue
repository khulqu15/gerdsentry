<template>
    <ion-page>
      <ion-content :fullscreen="true">
        <div class="drawer lg:drawer-open">
          <input id="my-drawer" type="checkbox" class="drawer-toggle" />
          <div class="drawer-content">
            <div class="container lg:pl-4">
                <div class="w-full pt-3 pb-1 px-3 rounded-b-2xl flex items-center justify-between bg-base-100">
                    <div>
                        <label for="my-drawer" class="btn btn-primary drawer-button lg:hidden">Menu</label>
                        <h1 class="text-xl mx-3 font-bold">{{ title }}</h1>
                    </div>
                    <div>
                        <div class="dropdown dropdown-bottom dropdown-end">
                            <div tabindex="0" role="button" class="avatar">
                                <div class="w-12 mask mask-squircle">
                                    <img src="https://daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg" />
                                </div>
                            </div>
                            <ul tabindex="0" class="dropdown-content z-[1] menu p-2 shadow bg-base-100 rounded-box w-52">
                                <li><a>Profile</a></li>
                                <li><a @click="$router.push({name: 'Login'})">Logout</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="pt-5">
                    <slot></slot>
                </div>
            </div>
          </div> 
          <div class="drawer-side">
            <label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
            <ul class="menu p-4 w-80 min-h-full bg-base-200 text-base-content">
              <li><a :class="{'bg-primary text-white': title == 'Dashboard'}">Dashboard</a></li>
              <li><a :class="{'bg-primary text-white': title == 'History'}">History Data</a></li>
              <li><a :class="{'bg-primary text-white': title == 'Setting'}">Pengaturan</a></li>
            </ul>
          </div>
        </div>
      </ion-content>
    </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
export default {
    name: 'DashboardLayout',
    components: {
        IonContent,
        IonHeader,
        IonPage,
        IonTitle,
        IonToolbar
    },
    props: {
        title: String
    }
}
</script>