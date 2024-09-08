<template>
    <div class="image-rating-post">
      <img :src="content.imageUrl" :alt="content.imageAlt" class="rating-image" />
      <div class="rating-stars">
        <v-icon
          v-for="star in 5"
          :key="star"
          :color="star <= content.rating ? 'amber' : 'grey lighten-2'"
          size="24"
        >
          mdi-star
        </v-icon>
      </div>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  
  const props = defineProps({
    content: {
      type: Object,
      required: true,
      validator: (value) => {
        return (
          typeof value.imageUrl === 'string' &&
          typeof value.imageAlt === 'string' &&
          typeof value.rating === 'number' &&
          value.rating >= 1 &&
          value.rating <= 5
        )
      }
    }
  })
  </script>
  
  <style>
  .image-rating-post {
    @apply w-full max-w-[929px] pt-3 flex flex-col justify-center items-center gap-2.5;
  }
  
  .rating-image {
    @apply w-full h-[283px] object-cover rounded-2xl;
  }
  
  .rating-stars {
    @apply flex justify-start items-start gap-1.5;
  }
</style>