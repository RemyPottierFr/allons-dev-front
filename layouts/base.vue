<template>
  <div class="pt-16 h-full relative">
    <div class="fixed h-16 flex flex-col w-full top-0 z-10">
      <div
        class="w-full bg-white p-2 shadow flex justify-center transition ease-in"
        :class="{ menuOpen: 'justify-between' }"
      >
        <nuxt-link to="/" class="h-12 w-12">
          <img src="/images/LogoBlog.png" alt="altText" />
        </nuxt-link>
        <button
          class="absolute-center text-3xl text-green-500 focus:outline-none"
          @click="(e) => handleMenu(e)"
        >
          <i class="fas fa-hamburger"></i>
        </button>
      </div>

      <transition name="bounce">
        <div
          v-if="menuOpen"
          class="absolute flex flex-col w-full shadow p-4 bg-white menu"
        >
          <nuxt-link to="/" class="text-2xl mb-2 font-Rmono flex">
            <div class="w-10">
              <i class="far fa-newspaper text-green-500"></i>
            </div>
            Articles
          </nuxt-link>
          <nuxt-link to="/" class="text-2xl mb-2 font-Rmono flex">
            <div class="w-10">
              <i class="fas fa-list text-green-500"></i>
            </div>
            Categories
          </nuxt-link>
          <nuxt-link to="/" class="text-2xl mb-2 font-Rmono flex">
            <div class="w-10">
              <i class="far fa-paper-plane text-green-500"></i>
            </div>
            Contact me !
          </nuxt-link>
          <nuxt-link to="/" class="text-2xl mb-2 font-Rmono flex">
            <div class="w-10">
              <i class="fab fa-github text-green-500"></i>
            </div>
            See others
          </nuxt-link>
        </div>
      </transition>
    </div>
    <nuxt class="min-h-screen"></nuxt>
    <footerCustom />
  </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'
import FooterCustom from '../components/FooterCustom'
export default {
  components: {
    FooterCustom
  },
  data() {
    return {
      menuOpen: false
    }
  },
  methods: {
    handleMenu(e) {
      const el = e.srcElement
      el.classList.toggle('top')
      this.menuOpen = !this.menuOpen
    }
  }
}
</script>

<style scoped>
.absolute-center {
  position: absolute;
  top: 50%;
  right: 1em;
  transform: translateY(-50%);
}
.menu {
  top: 100%;
}

.bounce-enter-active {
  animation: bounce-in 0.6s;
}
.bounce-leave-active {
  animation: bounce-in 0.6s reverse;
}
@keyframes bounce-in {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0%);
  }
}
</style>
