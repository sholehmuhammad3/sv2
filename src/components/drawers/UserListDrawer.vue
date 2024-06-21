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
          <v-row>
            <v-col>
              <v-badge
                  color="success"
                  inline
                  dot
              ></v-badge>
              2
            </v-col>
            <v-col>
              <v-badge
                  color="warning"
                  inline
                  dot
              ></v-badge>
              5
            </v-col>
            <v-col>
              <v-badge
                  color="grey-lighten-1"
                  inline
                  dot
              ></v-badge>
              3
            </v-col>
            <v-col>
              <v-icon size="14">mdi-account</v-icon>
              10
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>
      <v-list
          lines="two"
      >
        <v-list-subheader>Supervisor</v-list-subheader>
        <v-list-item
            v-for="x in 5"
            :key="x"
            :value="x"
            :title="`SPV Name ${x}`"
            density="compact"
            class="pa-1"
            style="min-height: 40px !important;"
        >
          <template v-slot:prepend>
            <v-avatar color="grey-lighten-1" size="20">
              <v-icon color="white">mdi-account</v-icon>
            </v-avatar>
          </template>
          <template v-slot:append>
            <v-badge
                color="success"
                inline
                dot
            ></v-badge>
          </template>
          <template #title>
            <div class="text-body-2">
              SPV {{ x }}
            </div>
          </template>
          <template #subtitle>
            <div class="text-caption">
              SPV .
            </div>
          </template>
        </v-list-item>
        <v-list-subheader>Agent</v-list-subheader>
        <v-list-item
            v-for="x in 5"
            :key="`agent-${x}`"
            :value="`agent-${x}`"
            :title="`Agent Name ${x}`"
            density="compact"
            class="pa-1"
            style="min-height: 40px !important;"
        >
          <template v-slot:prepend>
            <v-avatar color="grey-lighten-1" size="20">
              <v-icon color="white">mdi-account</v-icon>
            </v-avatar>
          </template>
          <template v-slot:append>
            <v-badge
                color="success"
                inline
                dot
            ></v-badge>
          </template>
          <template #title>
            <div class="text-body-2">
              Agent {{ x }}
            </div>
          </template>
          <template #subtitle>
            <div class="text-caption">
              Agent .
            </div>
          </template>
        </v-list-item>
      </v-list>
    </v-card>
  </v-navigation-drawer>
</template>

<style scoped>

</style>