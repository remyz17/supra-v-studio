<script setup>
import VTransitionFade from '@/components/VTransitionFade.vue'
import { RouterView } from 'vue-router'
import TheFooter from './layouts/TheFooter.vue'
import TheHeader from './layouts/TheHeader.vue'
</script>

<template>
  <TheHeader />
  <div class="shadow-sm flex-grow z-10 bg-black">
    <RouterView v-slot="{ Component }">
      <VTransitionFade>
        <component :is="Component" />
      </VTransitionFade>
    </RouterView>
  </div>
  <TheFooter />
</template>
