<template>
  <q-layout view="hHh LpR fFf">
    <q-header elevated class="header bg-white text-black">
      <q-toolbar class="toolbar flex justify-between">
        <div class="flex items-center">
          <q-btn flat round icon="menu" @click="toggleLeftDrawer" />
          <q-toolbar-title class="title flex items-center">
            <img class="logo" src="/yt-logo.svg" />
          </q-toolbar-title>
        </div>

        <div class="search-container">
          <q-input
            class="search"
            v-model="search"
            outlined
            rounded
            dense
            type="search"
            placeholder="Search"
          >
            <template v-slot:append>
              <q-icon class="search-icon" name="search" />
            </template>
          </q-input>
        </div>

        <div class="right-menu">
          <div class="right-icons">
            <q-icon>
              <img src="/src/assets/bell.svg" class="bell-icon" />
            </q-icon>
            <q-icon>
              <img src="/src/assets/video-camera.svg" class="bell-icon" />
            </q-icon>
          </div>
          <q-avatar>
            <img src="/account-avatar.jpg" />
          </q-avatar>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const leftDrawerOpen = ref(false);

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
};
</script>

<style scoped>
.header {
  height: 4rem;
}

.toolbar {
  height: 100%;
}

.title {
  height: 100%;
}

.logo {
  height: 2.2rem;
}

.search {
  width: 30vw;
}

.search-icon {
  display: hidden;
}

.bell-icon {
  height: 1.6rem;
  width: 1.6rem;
}

.right-menu {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.right-icons {
  display: none;
  gap: 2rem;
  align-items: center;
}

@media (min-width: 768px) {
  .right-icons {
    display: flex;
    gap: 2rem;
    align-items: center;
  }

  .search-icon {
    display: hidden;
    background-color: #d1d5db;
    height: 100%;
    width: 3.5rem;
    right: -0.7rem;
    border-top-right-radius: 1.3rem;
    border-bottom-right-radius: 1.3rem;
  }
}
</style>
