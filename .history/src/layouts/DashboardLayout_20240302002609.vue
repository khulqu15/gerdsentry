<template>
    <ion-page>
      <ion-content :fullscreen="true">
        <div class="drawer lg:drawer-open">
          <input id="my-drawer" type="checkbox" class="drawer-toggle" />
          <div class="drawer-content">
            <div class="container md:pl-4">
                <div class="w-full p-3 flex items-center justify-between">
                    <div>
                        <label for="my-drawer" class="btn btn-primary drawer-button">Menu</label>
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