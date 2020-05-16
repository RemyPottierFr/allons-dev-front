<template>
  <section class="relative p-6 background">
    <button type="button" @click="() => (loading = !loading)">
      {{ pageTitle }}
    </button>
    <div v-if="loading" class="flex flex-col">
      <div class="flex items-center w-full">
        <skeleton class="w-10 h-10 rounded-full"></skeleton>
        <skeleton class="ml-4 w-16 h-8 rounded"></skeleton>
        <skeleton class="ml-4 w-24 h-8 rounded"></skeleton>
        <skeleton class="ml-4 w-16 h-8 rounded"></skeleton>
      </div>
      <div class="mt-8 flex items-center flex-col">
        <skeleton class="w-10/12 h-10 rounded"></skeleton>
        <skeleton class="ml-auto mt-6 w-11/12 h-6 rounded"></skeleton>
        <div v-for="i in new Array(6)" :key="i" class="mt-4 h-6 w-full">
          <skeleton class="w-full h-full rounded"></skeleton>
        </div>
      </div>
    </div>
    <div v-else>
      hello
    </div>
  </section>
</template>

<script>
import Skeleton from '~/components/Skeleton'
export default {
  layout: 'base',
  components: {
    Skeleton
  },
  data() {
    return {
      pageTitle: '',
      loading: true
    }
  },
  mounted() {
    this.findArticle()
  },
  methods: {
    findArticle() {
      this.pageTitle = this.$route.params.title
    }
  }
}
</script>

<style scoped>
.background {
  background-color: #f3f3f3;
}
.bounce-enter-active {
  animation: bounce-out 0.6s;
}
.bounce-leave-active {
  animation: bounce-in 0.6s reverse;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
@keyframes bounce-in {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0%);
  }
}
@keyframes bounce-out {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(0%);
  }
}
</style>
