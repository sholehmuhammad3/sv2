<script setup lang="ts">
const props = defineProps([
    'isVisible'
])
</script>

<template>
  <v-navigation-drawer
      v-model="props.isVisible"
      border="none"
      style="top: 60px !important;"
      class="pa-2"
  >
    <v-card flat rounded="md">
      <v-card flat color="grey-lighten-3">
        <v-card-text class="pa-2 row">
          SoftPhone
        </v-card-text>
      </v-card>
      <v-list
          lines="two"
      >
      </v-list>
    </v-card>
  </v-navigation-drawer>
</template>

<style scoped>

</style>