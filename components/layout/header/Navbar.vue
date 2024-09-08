<template>
  <v-app-bar color="white" elevation="2" height="75">
    <v-container class="mx-auto px-0">
      <v-row no-gutters justify="center" align="center">
        <v-col cols="auto">
          <v-row no-gutters align="center" class="gap-12">
            <v-col v-for="(item, index) in menuItems" :key="index">
              <v-btn
                :color="item.active ? 'error' : ''"
                variant="text"
                class="px-2.5 py-2.5 rounded font-inter font-semibold text-base"
                :class="item.active ? 'text-error' : 'text-[#5B7083]'"
              >
                <v-icon
                  :icon="item.icon"
                  :color="item.active ? 'error' : '#5B7083'"
                  class="mr-1.25"
                  size="20"
                ></v-icon>
                {{ item.text }}
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<script setup>
import { ref } from "vue";

const menuItems = ref([
  { text: "Feed", icon: "mdi-rss", active: true },
  { text: "Courses", icon: "mdi-book-open-variant", active: false },
  { text: "Events", icon: "mdi-calendar", active: false },
  { text: "Podcast", icon: "mdi-podcast", active: false },
  { text: "Chat", icon: "mdi-chat", active: false },
]);
</script>
