<script lang="ts" setup>
import { CatResponse } from '~/types'

const { pending, error, data, refresh } = useFetch<CatResponse[]>(
  'https://api.thecatapi.com/v1/images/search?limit=10'
)
</script>

<template>
  <div>
    <h1>🐈Pretty Cats Here!</h1>
    <button class="refresh-button" @click="refresh">
      更新
    </button>
    <div v-if="!pending && data" class="content">
      <cat-card-list :cat-list="data" />
    </div>
  </div>
</template>

<style scoped>
h1{
  text-align: center;
}

.refresh-button{
  display: block;
  background-color: rgb(223, 133, 228);
  border: none;
  border-radius: 10px;
  margin: 0 auto 20px;
  padding: 5px 20vw;
}

.content {
  margin: auto;
}
</style>
