<template>
    <div class="event-banner">
      <div class="event-content">
        <div class="event-date">
          <div class="date-text">{{ formatDate(content.date) }}</div>
        </div>
        <div class="event-title">{{ content.title }}</div>
        <button class="ticket-button" @click="getTickets">Get tickets</button>
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
          value.date instanceof Date &&
          typeof value.title === 'string'
        )
      }
    }
  })
  
  const formatDate = (date) => {
    const day = date.getDate()
    const month = date.toLocaleString('default', { month: 'short' })
    const hours = date.getHours()
    const minutes = date.getMinutes().toString().padStart(2, '0')
    return `${day} ${month}\n${hours}:${minutes}`
  }
  
  const getTickets = () => {
    console.log('Getting tickets for:', props.content.title)
  }
  </script>
  
  <style scoped>
   .event-banner {
    @apply w-full max-w-[899px] h-[91px] px-[30.5px] py-[20px] bg-[#FB3F4A] shadow-md rounded-md overflow-hidden flex justify-center items-center;
  }
  
  .event-content {
    @apply w-full flex justify-between items-center;
  }
  
  .event-date {
    @apply px-2 py-2 bg-white rounded-sm overflow-hidden flex justify-center items-center;
  }
  
  .date-text {
    @apply text-[#FB3F4A] text-sm font-bold font-['Inter',sans-serif] whitespace-pre-line text-center;
  }
  
  .event-title {
    @apply text-white text-sm font-bold font-['Inter',sans-serif] flex-grow text-center mx-5;
  }
  
  .ticket-button {
    @apply px-[14px] py-[11px] bg-white rounded-md border-none overflow-hidden text-[#FB3F4A] text-sm font-bold font-['Inter',sans-serif] cursor-pointer;
  }
  
  @media (max-width: 768px) {
    .event-banner {
      @apply h-auto p-4;
    }
  
    .event-content {
      @apply flex-col gap-2.5;
    }
  
    .event-title {
      @apply my-2.5;
    }
  }
  </style>