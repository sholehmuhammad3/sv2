<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main class="pa-4">
    <VCard
        prepend-icon="$vuetify"
        subtitle="The #1 Vue UI Library"
        width="400"
    >
      <template v-slot:title>
        <span class="font-weight-black">Welcome to Vuetify</span>
      </template>

      <VCardText class="bg-surface-light pt-4">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi, ratione debitis quis est labore voluptatibus! Eaque cupiditate minima, at placeat totam, magni doloremque veniam neque porro libero rerum unde voluptatem!
      </VCardText>
    </VCard>
<!--    <TheWelcome />-->
  </main>
</template>
