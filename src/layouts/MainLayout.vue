<script setup lang="ts">
import { ref } from 'vue'
import UserListDrawer from "@/components/drawers/UserListDrawer.vue";
import SoftPhoneDrawer from "@/components/drawers/SoftPhoneDrawer.vue";
import SummaryDrawer from "@/components/drawers/SummaryDrawer.vue";
import IconUserGroup from "@/components/icons/IconUserGroup.vue";
import IconApp from "@/components/icons/IconApp.vue";
import IconSummary from "@/components/icons/IconSummary.vue";
import IconPhone from "@/components/icons/IconPhone.vue";
import IconLogo from "@/components/icons/IconLogo.vue";
import IconHome from "@/components/icons/IconHome.vue";
import IconTicket from "@/components/icons/IconTicket.vue";
import IconSetting from "@/components/icons/IconSetting.vue";
const userDrawer = ref(false)
const softPhoneDrawer = ref(false)
const summaryDrawer = ref(false)

const currentItem = ref('tab-Web')
const items = ref([
  'Web', 'Shopping', 'Videos', 'Images',
])
const more = [
  'News', 'Maps', 'Books', 'Flights', 'Apps',
]
const text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'

function addItem () {
  const removed = items.splice(0, 1)
}
const showDrawer = (type: string) => {
  switch (type) {
    case 'user':
      userDrawer.value = !userDrawer.value
      softPhoneDrawer.value = false
      summaryDrawer.value = false
      break
    case 'phone':
      userDrawer.value = false
      softPhoneDrawer.value = !softPhoneDrawer.value
      summaryDrawer.value = false
      break
    case 'summary':
      userDrawer.value = false
      softPhoneDrawer.value = false
      summaryDrawer.value = !summaryDrawer.value
      break

  }
}

</script>

<template>
  <v-layout>
    <v-app-bar
        color="white"
        density="compact"
        flat
    >
      <template v-slot:prepend>
        <div class="px-10">
          <icon-logo></icon-logo>
        </div>
      </template>

      <v-app-bar-title>
        <v-tabs
            v-model="currentItem"
            color="#4399D3"
        >
          <v-tab
              class="text-none"
              value="home"
          >
            <template #prepend>
              <v-icon>
                <icon-home></icon-home>
              </v-icon>
            </template>
            <template #default>
              Main Dashboard
            </template>
          </v-tab>

          <v-btn
              class="align-self-center me-4 text-none"
              height="100%"
              rounded="0"
              value="ticket"
          >
            <v-icon>
              <icon-ticket></icon-ticket>
            </v-icon>
            <span class="mx-2">Tickets</span>
            <v-icon>mdi-chevron-down</v-icon>
            <v-menu activator="parent">
              <v-list>
                <v-list-item value="item-1">
                  <v-list-item-title>Item 1</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </v-btn>

          <v-btn
              class="align-self-center me-4 text-none"
              height="100%"
              rounded="0"
              value="ticket"
          >
            <v-icon>
              <icon-summary></icon-summary>
            </v-icon>
            <span class="mx-2">Reports</span>
            <v-icon>mdi-chevron-down</v-icon>
            <v-menu activator="parent">
              <v-list>
                <v-list-item value="item-1">
                  <v-list-item-title>Item 1</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </v-btn>

          <v-btn
              class="align-self-center me-4 text-none"
              height="100%"
              rounded="0"
              value="ticket"
          >
            <v-icon>
              <icon-setting></icon-setting>
            </v-icon>
            <span class="mx-2">Settings</span>
            <v-icon>mdi-chevron-down</v-icon>
            <v-menu activator="parent">
              <v-list>
                <v-list-item value="item-1">
                  <v-list-item-title>Item 1</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </v-btn>
        </v-tabs>
      </v-app-bar-title>

      <template v-slot:append>
        <v-btn icon="mdi-dots-vertical"></v-btn>
      </template>
    </v-app-bar>

    <v-navigation-drawer
        permanent
        rail
        style="top: 60px !important"
    >
      <v-list
      >
        <v-list-item
            value="user"
            @click="showDrawer('user')"
            class="pa-0"
        >
          <template #default>
            <div class="text-center">
              <v-icon>
                <icon-user-group></icon-user-group>
              </v-icon>
              <div class="font-8">User</div>
            </div>
          </template>
        </v-list-item>

        <v-list-item
            value="dashboard"
            class="pa-0"
        >
          <template #default>
            <div class="text-center">
              <v-icon>
                <icon-app></icon-app>
              </v-icon>
              <div class="font-8">App</div>
            </div>
          </template>
        </v-list-item>

        <v-list-item
            value="summary"
            @click="showDrawer('summary')"
            class="pa-0"
        >
          <template #default>
            <div class="text-center">
              <v-icon>
                <icon-summary></icon-summary>
              </v-icon>
              <div class="font-8">Summary</div>
            </div>
          </template>
        </v-list-item>
        <v-list-item
            value="phone"
            @click="showDrawer('phone')"
            class="pa-0"
        >
          <template #default>
            <div class="text-center">
              <v-icon>
                <icon-phone></icon-phone>
              </v-icon>
              <div class="font-8">Soft Phone</div>
            </div>
          </template>

        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <summary-drawer :is-visible="summaryDrawer"></summary-drawer>

    <user-list-drawer :is-visible="userDrawer"></user-list-drawer>

    <soft-phone-drawer :is-visible="softPhoneDrawer"></soft-phone-drawer>

    <v-main>
      <RouterView />
    </v-main>
  </v-layout>
</template>

<style scoped>

</style>