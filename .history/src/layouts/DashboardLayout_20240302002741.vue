<template>
    <ion-page>
      <ion-content :fullscreen="true">
        <div class="drawer lg:drawer-open">
          <input id="my-drawer" type="checkbox" class="drawer-toggle" />
          <div class="drawer-content">
            <div class="container lg:pl-4">
                <div class="w-full p-3 flex items-center justify-between">
                    <div>
                        <label for="my-drawer" class="btn btn-primary drawer-button lg:hidden">Menu</label>
                    </div>
                    <div>
                        <div class="avatar">
                            <div class="w-24 mask mask-squircle">
                                <img src="https://daisyui.com/images/stock/photo-1534528741775-53994a69daeb.jpg" />
                            </div>
                        </div>
                    </div>
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