<template>
  <Navigation />
  <div class="container">
    <router-view v-slot="{Component}">
      <transition name="fade" mode="out-in"> 
        <component :is="Component"  :key="$route.path"></component>
      </transition>
    </router-view>
  </div>
</template>

<script>
import Navigation from "@/components/Navigation.vue";
export default {
  components: {
    Navigation,
  },
};
</script>


<style lang="css">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>