<template>
  <q-page class="">
    <div class="video-cards">
      <div
        class="video-card-container"
        v-for="(video, index) in videos"
        :key="index"
      >
        <VideoCard :video="video" />
      </div>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import VideoCard from 'src/components/VideoCard.vue';

defineOptions({
  name: 'IndexPage',
});

const videos = ref([
  {
    title: 'video 1',
    account_name: 'account 1',
    thumbnail: 'https://cdn.quasar.dev/img/parallax1.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 2',
    account_name: 'account 2',
    thumbnail: 'https://cdn.quasar.dev/img/parallax1.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 3',
    account_name: 'account 3',
    thumbnail: 'https://cdn.quasar.dev/img/parallax2.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 4',
    account_name: 'account 4',
    thumbnail: 'https://cdn.quasar.dev/img/parallax2.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 5',
    account_name: 'account 5',
    thumbnail: 'https://cdn.quasar.dev/img/mountains.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 6',
    account_name: 'account 6',
    thumbnail: 'https://cdn.quasar.dev/img/mountains.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },

  {
    title: 'video 7',
    account_name: 'account 2',
    thumbnail: 'https://cdn.quasar.dev/img/quasar.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 8',
    account_name: 'account 2',
    thumbnail: 'https://cdn.quasar.dev/img/quasar.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
  {
    title: 'video 9',
    account_name: 'account 2',
    thumbnail: 'https://cdn.quasar.dev/img/parallax1.jpg',
    account_avatar: '/account-avatar.jpg',
    views: 0,
  },
]);
</script>

<style>
.video-cards {
  padding: 10px;
  display: grid;
  gap: 20px;
  row-gap: 20px;
}

@media (min-width: 768px) {
  .video-cards {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 20px;
    row-gap: 20px;
  }
}

@media (min-width: 1024px) {
  .video-cards {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 20px;
    row-gap: 20px;
  }
}

.video-card-container {
  min-width: 250px;
}
</style>
