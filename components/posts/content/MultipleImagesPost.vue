<template>
    <div class="multiple-images-post">
      <div v-for="(row, rowIndex) in content.rows" :key="rowIndex" class="image-row">
        <div v-for="(image, imageIndex) in row" :key="imageIndex" class="image-container">
          <div class="image-indicator" :class="{ 'active': image.active }">
            <div class="indicator-inner"></div>
          </div>
          <img :src="image.url" :alt="image.alt" class="post-image" :class="{ 'large': imageIndex === 0 }" />
        </div>
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
        return Array.isArray(value.rows) && value.rows.every(row => 
          Array.isArray(row) && row.every(image => 
            typeof image.url === 'string' && 
            typeof image.alt === 'string' && 
            typeof image.active === 'boolean'
          )
        )
      }
    }
  })
  </script>
  
  <style scoped>
  .multiple-images-post {
    @apply w-full max-w-[929px] pt-3 flex flex-col justify-start items-start gap-2.5;
  }
  
  .image-row {
    @apply w-full max-w-[800px] rounded-[10px] flex justify-center items-start gap-2.5;
  }
  
  .image-container {
    @apply flex-1 flex flex-col justify-start items-center gap-2.5;
  }
  
  .image-indicator {
    @apply w-[25px] h-[25px] p-[5px] bg-[#C5C5C5] rounded-full overflow-hidden flex justify-center items-center;
  }
  
  .indicator-inner {
    @apply w-[15px] h-[15px] bg-[#A8A8A8] rounded-full;
  }
  
  .image-indicator.active .indicator-inner {
    @apply bg-[#FB3F4A];
  }
  
  .post-image {
    @apply w-[310px] h-[283px] rounded-2xl object-cover;
  }
  
  .post-image.large {
    @apply w-full max-w-[480px];
  }
  </style>