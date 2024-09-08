<template>
    <div class="media-post">
      <v-img
        v-if="content.type === 'image'"
        :src="content.url"
        :alt="content.alt"
        cover
        max-height="400"
      ></v-img>
      <video
        v-else-if="content.type === 'video'"
        :src="content.url"
        :poster="content.poster"
        controls
        class="w-full max-h-[400px]"
      ></video>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  
  const props = defineProps({
    content: {
      type: Object,
      required: true,
    },
  })
  </script>
  
  <style scoped>
  .media-post {
    @apply w-full rounded-lg overflow-hidden;
  }
  </style>