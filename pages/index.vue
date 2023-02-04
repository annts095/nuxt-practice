<script lang="ts" setup>
import { CatResponse } from '~/types'

const { pending, error, data } = useFetch<CatResponse[]>(
  'https://api.thecatapi.com/v1/images/search?limit=10'
)
</script>

<template>
  <div v-if="!pending && data" class="content">
    <cat-card-list :cat-list="data" />
  </div>
</template>

<style scoped>
.content {
  margin: auto;
}
</style>
