<template>
  <v-navigation-drawer location="right" width="320">
    <div class="p-5 space-y-5">
      <div class="bg-gray-50 rounded-lg">
        <div class="flex justify-between items-center mb-4">
          <h2 class="text-gray-700 font-bold">Upcoming events</h2>
          <v-btn variant="text" class="text-blue-600 font-semibold text-sm"
            >See all</v-btn
          >
        </div>
        <v-date-picker
          v-model="selectedDate"
          
          :show-current="false"
          :first-day-of-week="1"
        >
          <template v-slot:day="{ date }">
            <v-btn
              :class="{
                'bg-red-500 text-white': isSpecialDate(date, 'red'),
                'bg-teal-500 text-white': isSpecialDate(date, 'teal'),
              }"
              :disabled="date.day === 13"
            >
              {{ date.day }}
            </v-btn>
          </template>
        </v-date-picker>
      </div>
      <div class="bg-gray-50 rounded-lg p-4">
        <div class="flex justify-between items-center mb-4">
          <h2 class="text-gray-700 font-bold">Who to follow</h2>
          <v-btn variant="text" class="text-blue-600 font-semibold text-sm"
            >See all</v-btn
          >
        </div>
        <div class="space-y-1">
          <v-card
            v-for="user in usersToFollow"
            :key="user.username"
            class="!p-3"
          >
            <div class="flex items-center justify-between">
              <div class="flex items-center space-x-3">
                <v-avatar :image="user.avatar" size="48" />
                <div>
                  <p class="font-bold text-sm">{{ user.name }}</p>
                  <p class="text-gray-500 text-xs">@{{ user.username }}</p>
                </div>
              </div>
              <v-btn color="error" variant="outlined" size="small"
                >Follow</v-btn
              >
            </div>
          </v-card>
        </div>
      </div>
    </div>
  </v-navigation-drawer>
</template>

<script setup>
import { ref } from "vue";
import hotjar from "~/assets/images/avatars/hotjar.png";
import mailchimp from "~/assets/images/avatars/mailchimp.png";
import pinkfong from "~/assets/images/avatars/pinkfong.png";
const selectedDate = ref(new Date());

const usersToFollow = [
  { name: "Pinkfong", username: "tko", avatar: pinkfong },
  { name: "Mailchimp", username: "bawa", avatar: mailchimp },
  { name: "Hotjar", username: "ansarigee", avatar: hotjar },
];

const isSpecialDate = (date, color) => {
  const specialDates = {
    red: [5,10],
    teal: [18, 30],
  };
  return specialDates[color].includes(date.day);
};
</script>

