<script setup>
import {RouterView} from "vue-router";
import SiteNavigation from "@/components/SiteNavigation.vue";
</script>

<template>
  <div class="flex flex-col min-h-screen font-Roboto bg-weather-primary">
    <SiteNavigation/>
    <RouterView v-slot="{ Component }">
      <transition name="zoom-fade" mode="out-in">
        <component :is="Component"/>
      </transition>
    </RouterView>
  </div> 
</template>

<style>
.zoom-fade-enter-active,
.zoom-fade-leave-active {
  transition: transform 0.35s, opacity 0.28s ease-in-out;
}
.zoom-fade-enter {
  transform: scale(0.97);
  opacity: 0;
}

.zoom-fade-leave-to {
  transform: scale(1.03);
  opacity: 0;
}
</style>
