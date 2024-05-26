<template>
  <q-layout view="hHh lpR fFf">
    <audio id="background-music" autoplay loop>
      <source src="./components/ssstik.io_1714998999401 (1).mp3" type="audio/mpeg">
      Your browser does not support the audio element.
    </audio>
    <q-header elevated class="bg-navy text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          <q-avatar>
            <img src="https://i.pinimg.com/564x/be/be/5f/bebe5f3e5af8b17c159179dc295f1544.jpg">
          </q-avatar>
          laptop by Rizh
        </q-toolbar-title>
      </q-toolbar>
      <q-tabs align="left">
        <q-route-tab to="/belanja" label="Belanja" />
        <q-route-tab to="/profil" label="Profil" />
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <div class="q-pa-md row items-start q-gutter-md">
        <q-card class="my-card">
          <img src="https://i.pinimg.com/564x/fa/66/44/fa6644dca5b822f57cdec0c95e19abe9.jpg">
          <q-card-section>
            <div class="text-h6">Laptop Impian kita semua</div>
            <div class="text-subtitle2">by Rizh</div>
          </q-card-section>
          <q-card-section class="q-pt-none">
            {{ lorem }}
          </q-card-section>
        </q-card>
      </div>

      <div class="q-pa-md row items-start q-gutter-md">
        <q-card class="my-card">
          <img src="https://i.pinimg.com/564x/a6/d2/b5/a6d2b58caf75d258ecf062daba3df35f.jpg">
          <q-card-section>
            <div class="text-h6">Laptop keren</div>
            <div class="text-subtitle2">by Rizh</div>
          </q-card-section>
          <q-card-section class="q-pt-none">
            {{ lorem }}
          </q-card-section>
        </q-card>
      </div>
      <div class="q-pa-md row items-start q-gutter-md">
        <q-card class="my-card">
          <img src="https://i.pinimg.com/564x/8c/e7/99/8ce79974038335c2f5bd1f2bee4d3df8.jpg">
          <q-card-section>
            <div class="text-h6">Laptop impian masa depan</div>
            <div class="text-subtitle2">by Rizh</div>
          </q-card-section>
          <q-card-section class="q-pt-none">
            {{ lorem }}
          </q-card-section>
        </q-card>
      </div>
    </q-drawer>

    <q-page-container>
  <router-view />
  <div class="q-pa-md">
    <q-carousel
      animated
      v-model="slide"
      arrows
      navigation
      infinite
      height="100vh"
      autoplay
      autoplay-interval="1000"
    >
      <q-carousel-slide :name="1" img-src="https://i.pinimg.com/564x/5e/18/8e/5e188e03791a1eca5ce4e6b98666ad38.jpg" />
      <q-carousel-slide :name="2" img-src="https://i.pinimg.com/564x/eb/35/4e/eb354e8c2b1c8ba61fb8700708310464.jpg" />
      <q-carousel-slide :name="3" img-src="https://i.pinimg.com/564x/f2/eb/5b/f2eb5ba30d3444034f4b2e801559787c.jpg" />
      <q-carousel-slide :name="4" img-src="https://i.pinimg.com/736x/2b/97/99/2b9799e6efbc3f6345d26997268c605c.jpg" />
      <q-carousel-slide :name="5" img-src="https://c4.wallpaperflare.com/wallpaper/49/381/270/computer-game-gaming-laptop-wallpaper-preview.jpg" />
    </q-carousel>
  </div>
</q-page-container>


    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://i.pinimg.com/564x/be/be/5f/bebe5f3e5af8b17c159179dc295f1544.jpg">
          </q-avatar>
          <div>RyzNoCure.</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const leftDrawerOpen = ref(false);
    const slide = ref(1);

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value;
    };

    return {
      leftDrawerOpen,
      slide,
      toggleLeftDrawer
    };
  }
};
</script>

<style>
.bg-navy {
  background-color: navy;
}
.card-image {
  height: 200px;
}
.q-carousel-slide img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}
</style>
