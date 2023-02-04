<script lang="ts" setup>
import { CatResponse } from '~/types'

interface Props {
  catData: CatResponse;
}

defineProps<Props>()
</script>

<template>
  <div class="card-img-wrapper">
    <img
      class="card-img"
      :src="catData.url"
      alt="cute cat"
      :data-testid="catData.id"
    >
  </div>
</template>

<style scoped>

.card-img-wrapper {
  width: 100%;
}
.card-img {
  border-radius: 8px;
  width: 100%;
  aspect-ratio: 1 / 1;
  object-fit: cover;
}
</style>
