<template>
    <ion-page>
      <ion-content :fullscreen="true">
        <div id="container" class="min-h-screen bg-base-100 flex items-center text-base-content relative">
          <img src="/wallpaper.jpg" class="w-full h-full absolute left-0 top-0 object-cover object-center" alt="">
          <div class="w-full h-full absolute left-0 right-0 bg-gradient-to-b from-primary/30 to-primary"></div>
          <div class="w-full bottom-0 left-0 p-4 flex justify-center">
            <div class="w-full bg-base-100/40 max-w-lg text-white p-4 backdrop-blur-md rounded-xl">
              <div class="text-xl font-bold">Register to GERDSentry</div>
              <p class="text-sm mt-1 mb-4">Regist and get medic data with easily</p>
              <form @submit="onSubmit($event)">
                <div class="form_control">
                  <label for="name" class="text-sm">Name</label>
                  <input id="name" type="text" required placeholder="Enter your email here" class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
                <div class="form_control mt-3">
                  <label for="name" class="text-sm">Name</label>
                  <input id="name" type="text" required placeholder="Enter your email here" class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
                <div class="form_control mt-3">
                  <label for="email" class="text-sm">Email</label>
                  <input id="email" type="email" required placeholder="Enter your email here" class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
                <div class="form_control mt-3">
                  <label for="password" class="text-sm">Password</label>
                  <input id="password" type="password" placeholder="Enter your password here" required class="input mt-1 input-bordered w-full text-base-content bg-base-200/30">
                </div>
                <div class="flex items-center form_control gap-2 mt-3">
                  <input id="show_password" type="checkbox" @change="showPassword()" class="checkbox">
                  <label for="show_password">Show Password</label>
                </div>
                <button type="submit" class="btn btn-primary w-full mt-3">Register</button>
                <button @click="$router.push({name: 'Login'})" type="button" class="btn btn-ghost btn-sm w-full mt-3">Login</button>
              </form>
            </div>
          </div>
        </div>
      </ion-content>
    </ion-page>
  </template>
  
  <script setup lang="ts">
  import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
  import { onMounted, ref } from 'vue';
  import { useRouter } from 'vue-router';

  const router = useRouter();
  const email = ref('');
  const password = ref('');
  
  function showPassword() {
    const passwordInput = document.getElementById('password') as HTMLInputElement;
    console.log(passwordInput)
    if (passwordInput) {
      if (passwordInput.getAttribute('type') == 'password') {
        passwordInput.setAttribute('type', 'text');
      } else {
        passwordInput.setAttribute('type', 'password');
      }
    }
  }

  function onSubmit(event: Event) {
    event.preventDefault();
    router.push({name: 'Home'});
  }
  
  onMounted(() => {
  
  });
  
  </script>