<template>
  <v-navigation-drawer width="200">
    <v-list class="pa-2">
      <v-list-subheader class="text-base font-semibold bg-[#F7F9FA] rounded mb-2 py-2.5">
        Feed topics
      </v-list-subheader>

      <v-list-item
        v-for="(item, index) in feedTopics"
        :key="index"
        :active="item.active"
        active-color="error"
        rounded="sm"
        class="mb-2"
      >
        <v-list-item-title 
          class="text-base font-medium"
          :class="item.active ? 'text-white' : 'text-black'"
        >
          {{ item.title }}
        </v-list-item-title>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
import { ref } from 'vue';

const feedTopics = ref([
  { title: 'All', active: true },
  { title: 'Cooking feed', active: false },
  { title: 'Q&A', active: false },
  { title: 'Announcement', active: false },
  { title: 'Cashout', active: false },
  { title: 'Course Abc', active: false },
]);
</script>

<style>
.v-list-item--active {
  background-color: #FB3F4A !important;
}

.v-list-item {
  min-height: 40px !important;
}
</style>