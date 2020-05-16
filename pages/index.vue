<template>
  <div class="w-full p-8 background">
    <div class="flex item-center justify-between">
      <div class="w-4/12 flex flex-col">
        <img src="/images/LogoBlog.png" alt="altText" class="mt-auto mb-auto" />
      </div>
      <div class="w-7/12 flex flex-col">
        <h1 class="font-Rmono font-semibold text-xl">Rémy Pottier</h1>
        <h2 class="font-Rmono text-md">
          Développeur web autodidacte et freelance.
        </h2>
      </div>
    </div>
    <button type="button" @click="() => (loading = !loading)">change</button>
    <div v-if="loading" class="mt-8">
      <div v-for="i in new Array(4)" :key="i">
        <div class="bg-white rounded shadow p-4 mt-4 flex items-center">
          <div class="w-12 h-12 mr-6">
            <skeleton class="w-12 h-12 rounded-full mr-6"></skeleton>
          </div>
          <skeleton class="w-full h-8 rounded"></skeleton>
        </div>
      </div>
    </div>
    <div v-else class="mt-8">
      <div v-for="i in new Array(4)" :key="i">
        <div
          class="bg-white rounded shadow p-4 mt-4 flex flex-col overflow-hidden"
        >
          <div class="flex items-center justify-start">
            <img
              src="/images/LogoBlog.png"
              alt="altText"
              class="w-12 h-12 mr-4"
            />
            <div class="flex overflow-x-scroll h-full">
              <h3 class="text-xl">☕ 1 minute</h3>
            </div>
          </div>
          <span class="font-Rmono text-xl cutted w-full">
            C'est un titre super cool mais un peu long
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Skeleton from '../components/Skeleton'
export default {
  layout: 'base',
  components: {
    Skeleton
  },
  data() {
    return {
      loading: true
    }
  }
}
</script>
<style scoped>
.background {
  background-color: #f3f3f3;
}
</style>
