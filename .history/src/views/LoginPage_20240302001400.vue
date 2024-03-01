<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <div id="container" class="min-h-screen bg-base-100 text-base-content relative overflow-hidden">
        <img src="/wallpaper.jpg" class="w-full h-full absolute left-0 top-0 object-cover object-center" alt="">
        <div class="w-full h-full absolute left-0 right-0 bg-gradient-to-b from-primary/30 to-primary"></div>
        <div class="absolute w-full h-full bottom-0 left-0 p-4 flex items-center justify-center">
          <div class="w-full bg-base-100/40 text-white p-4 max-w-lg backdrop-blur-md rounded-xl">
            <div class="text-xl font-bold">Welcome to GERDSentry</div>
            <p class="text-sm mt-1 mb-4">Sign in and get medic data with easily</p>
            <form>
              <div class="form_control">
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
              <button type="submit" class="btn btn-primary w-full mt-3">Login</button>
              <button type="button" class="btn w-full bg-black text-white mt-3">Login With Google</button>
              <button @click="$router.push({name: 'Register'})" type="button" class="btn btn-ghost btn-sm w-full mt-3">Register</button>
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

onMounted(() => {

});

</script>