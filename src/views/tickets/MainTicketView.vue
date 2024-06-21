<script setup lang="ts">
import { ref } from 'vue'
import FilterTicketView from "@/views/tickets/FilterTicketView.vue";
const tab = ref(null)
const text = ref('Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut' +
    'labore et dolore magna aliqua. Ut enim ad minim veniam,' +
    'quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.')
</script>

<template>
  <main class="pa-4">
    <v-row>
      <v-col class="v-col-1"></v-col>
      <v-col class="v-col-8">
        <v-sheet>
          <v-card>
            <v-tabs
                v-model="tab"
                align-tabs="center"
                stacked
                fixed-tabs
                density="compact"
            >
              <v-tab
                  value="tab-1"
                  class="text-none"
              >
                New
                <div>100</div>
              </v-tab>
              <v-tab
                  value="tab-2"
                  class="text-none"
              >
                Open
                <div>100</div>
              </v-tab>
              <v-tab
                  value="tab-3"
                  class="text-none"
              >
                Progress
                <div>100</div>
              </v-tab>
              <v-tab
                  value="tab-4"
                  class="text-none"
              >
                Closed
                <div>100</div>
              </v-tab>
              <v-tab
                  value="tab-5"
                  class="text-none"
              >
                All
                <div>100</div>
              </v-tab>
              <v-tab
                  value="tab-6"
                  class="text-none"
              >
                Pending
                <div>100</div>
              </v-tab>
            </v-tabs>
          </v-card>
        </v-sheet>
      </v-col>
      <v-col></v-col>
    </v-row>
    <v-tabs-window v-model="tab" class="mt-4">
      <v-tabs-window-item
          v-for="i in 3"
          :key="i"
          :value="'tab-' + i"
      >
        <v-card
            class="mx-auto"
        >
          <v-card-text class="pa-2">
            <div class="float-left">
              <v-checkbox density="compact"></v-checkbox>
            </div>
            <div>
              <v-card
                  flat
                  class="mx-auto"
                  prepend-icon="mdi-account"
                  subtitle="prepend-icon and append-icon"
                  title="Icons"
              >
                <v-card-text>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.</v-card-text>
              </v-card>
            </div>
          </v-card-text>
        </v-card>
      </v-tabs-window-item>
    </v-tabs-window>
    <filter-ticket-view />
  </main>
</template>

<style scoped>

</style>