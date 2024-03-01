<template>
    <ion-page>
      <ion-content :fullscreen="true">
        <div class="drawer lg:drawer-open">
          <input id="my-drawer" type="checkbox" class="drawer-toggle" />
          <div class="drawer-content">
            <div class="container lg:pl-4">
                <div class="w-full pt-3 pb-1 px-3 flex items-center justify-between bg-base-100">
                    <div>
                        <label for="my-drawer" class="btn btn-primary drawer-button lg:hidden">Menu</label>
                    </div>
                    <div>
                        <div class="avatar">
                            <div class="w-12 mask mask-squircle">
                                <img src="https://daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg" />
                            </div>
                        </div>
                    </div>
                </div>
                <div>
                    <slot></slot>
                </div>
            </div>
          </div> 
          <div class="drawer-side">
            <label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
            <ul class="menu p-4 w-80 min-h-full bg-base-200 text-base-content">
              <li><a>Dashboard</a></li>
              <li><a>Sidebar Item 2</a></li>
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
    }
}
</script>