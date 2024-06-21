<script setup lang="ts">

</script>

<template>
  <v-card
      class="mx-auto"
      subtitle="prepend and append"
      title="Icons"
  >
    <template v-slot:prepend>
      <v-icon color="primary" icon="mdi-account"></v-icon>
    </template>
    <template v-slot:append>
      <v-icon color="success" icon="mdi-check"></v-icon>
    </template>
    <v-card-text>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.</v-card-text>
  </v-card>
</template>

<style scoped>

</style>