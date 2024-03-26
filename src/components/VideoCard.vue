<template>
  <div class="my-card">
    <q-card class="q-card">
      <img class="card-image" :src="props.video.thumbnail" />
    </q-card>

    <div class="card-details">
      <q-avatar>
        <img :src="props.video.account_avatar" />
      </q-avatar>
      <div class="video-details">
        <span class="title">{{ props.video.title }}</span>

        <div class="account-views">
          <span class="account">{{ props.video.account_name }}</span>
          <span class="views">{{ props.video.views }} views • 1 day</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['video']);
</script>

<style scoped>
.my-card {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  width: 100%;
}

.q-card {
  border-radius: 0.8rem;
}
.card-image {
  aspect-ratio: 16/9;
  min-width: 250px;
}

.card-details {
  display: flex;
  gap: 0.4rem;
}

.video-details {
  display: flex;
  padding-right: 24px;
  flex-direction: column;
  gap: 0.04rem;
}

.title {
  font-size: 1.3rem;
  line-height: 1.5rem;
  font-weight: 500;
}
.account-views {
  font-size: 1rem;
  line-height: 1.2rem;
  font-weight: 400;
  display: flex;
  flex-direction: column;
  gap: 0.01rem;
  color: #374151;
}
</style>
