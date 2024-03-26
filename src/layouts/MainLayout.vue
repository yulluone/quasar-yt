<template>
  <q-layout view="hHh LpR fFf">
    <q-header elevated class="header bg-white text-black">
      <q-toolbar class="toolbar flex justify-between">
        <div class="flex items-center">
          <q-btn flat round icon="o_menu" @click="toggleLeftDrawer" />
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
              <q-icon class="search-icon" name="o_search" />
            </template>
          </q-input>
        </div>

        <div class="right-menu">
          <div class="right-icons">
            <q-icon name="o_notifications" size="2.2em" />
            <q-icon name="o_video_call" size="2.2em" />
          </div>
          <q-avatar>
            <img src="/account-avatar.jpg" />
          </q-avatar>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" :width="200" side="left">
      <q-list padding class="menu-list">
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon size="md" name="o_home" outlined />
          </q-item-section>
          <q-item-section class="menu-label"> Home </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon size="md" name="o_music_video" />
          </q-item-section>
          <q-item-section class="menu-label"> Shorts </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon size="md" name="o_subscriptions" />
          </q-item-section>
          <q-item-section class="menu-label"> Home </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon size="md" name="o_video_library" />
          </q-item-section>
          <q-item-section class="menu-label"> You </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon size="md" name="o_history" />
          </q-item-section>
          <q-item-section class="menu-label"> History </q-item-section>
        </q-item>
      </q-list>
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
  display: none;
}

.search-icon {
  background-color: #d1d5db;
  height: 96%;
  width: 3.5rem;
  right: -0.65rem;
  border-top-right-radius: 1.6rem;
  border-bottom-right-radius: 1.6rem;
  align-self: center;
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
    gap: 1rem;
    align-items: center;
    color: #374151;
  }

  .search {
    display: block;
    width: 30vw;
  }

  .menu-list {
    color: #374151;
    padding-top: 2rem;
  }

  .menu-label {
    font-size: 1rem;
    font-weight: 500;
  }
}
</style>
