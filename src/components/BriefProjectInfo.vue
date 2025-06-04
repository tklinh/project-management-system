<template>
  <a-card :loading="loading" :title="cardTitle">
    <a-row :gutter="[16, 16]">
      <a-col :xs="24" :sm="8">
        <a-image
          :src="imageSrc"
          :alt="cardTitle"
          :width="200"
          :height="200"
          class="card-image"
        />
      </a-col>
      <a-col :xs="24" :sm="16">
        <a-list size="small">
          <a-list-item><strong>Địa điểm:</strong> {{ info.location }}</a-list-item>
          <a-list-item><strong>Quy mô:</strong> {{ info.area }}</a-list-item>
          <a-list-item><strong>Tình trạng:</strong> {{ info.status }}</a-list-item>
        </a-list>
      </a-col>
    </a-row>
  </a-card>
</template>
<script lang="ts" setup>
import { onUnmounted, ref } from "vue";

interface Info {
  location: string;
  area: string;
  status: string;
}

const props = defineProps<{
  cardTitle: string;
  imageSrc: string;
  info: Info;
}>();

const loading = ref(true);

let timer: ReturnType<typeof setTimeout> | null = null;

const getRandomDelay = (): number => {
  return Math.floor(Math.random() * (2000 - 500 + 1)) + 500;
};

const toggleLoading = () => {
  if (timer) {
    clearTimeout(timer);
  }
  timer = setTimeout(() => {
    loading.value = false;
  }, getRandomDelay());
};

onUnmounted(() => {
  if (timer) {
    clearTimeout(timer);
  }
});

toggleLoading();
</script>
<style scoped>
.info-card {
  max-width: 800px;
  margin: 16px auto;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card-image {
  object-fit: cover;
  border-radius: 8px;
}

/* Ensure image and text align properly on smaller screens */
@media (max-width: 576px) {
  .card-image {
    width: 100%;
    height: auto;
  }
}
</style>
