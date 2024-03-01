<template>
  <dashboard-layout-vue>
    <div>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis odio mollitia est, nam, veniam at doloremque fugit obcaecati vitae officiis itaque tempore error quas aperiam esse ab consectetur recusandae laudantium?
    </div>
  </dashboard-layout-vue>
</template>

<script setup lang="ts">
import DashboardLayoutVue from '@/layouts/DashboardLayout.vue';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
