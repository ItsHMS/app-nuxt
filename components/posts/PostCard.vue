<template>
    <v-card class="post-card">
      <div class="post-header">
        <div class="posted-in">
          <span class="text-sm font-bold text-gray-600">Posted in {{ post.feed }}</span>
        </div>
      </div>
      <div class="post-content">
        <v-avatar size="48">
          <v-img :src="post.authorAvatar" alt="Author Avatar"></v-img>
        </v-avatar>
        <div class="post-details">
          <div class="author-info">
            <div class="author-name-time">
              <span class="font-bold">{{ post.authorName }}</span>
              <span class="text-gray-600">{{ post.authorUsername }}</span>
              <span class="text-gray-600">·</span>
              <span class="text-gray-600">{{ post.timeAgo }}</span>
            </div>
            <v-btn icon variant="text" size="small">
              <v-icon>mdi-dots-horizontal</v-icon>
            </v-btn>
          </div>
          <div class="post-text">
            <span>{{ post.text }}</span>
          </div>
          <component :is="getContentComponent(post.contentType)" :content="post.content" />
          <div class="post-actions">
            <v-btn icon variant="text" size="small">
              <v-icon>mdi-comment-outline</v-icon>
              <span class="ml-1 text-gray-600">{{ post.commentCount }}</span>
            </v-btn>
            <v-btn icon variant="text" size="small">
              <v-icon>mdi-repeat</v-icon>
              <span class="ml-1 text-gray-600">{{ post.shareCount }}</span>
            </v-btn>
            <v-btn icon variant="text" size="small">
              <v-icon>mdi-heart-outline</v-icon>
            </v-btn>
          </div>
        </div>
      </div>
    </v-card>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  import MediaPost from '~/components/posts/content/MediaPost.vue'
  import ImageRatingPost from '~/components/posts/content/ImageRatingPost.vue'
  import EventBannerPost from '~/components/posts/content/EventBannerPost.vue'
  import MultipleImagesPost from '~/components/posts/content/MultipleImagesPost.vue'
  
  const props = defineProps({
    post: {
      type: Object,
      required: true,
    },
  })
  
  const getContentComponent = (contentType) => {
    switch (contentType) {
      case 'image':
      case 'video':
        return MediaPost
      case 'imageRating':
        return ImageRatingPost
      case 'eventBanner':
        return EventBannerPost
      case 'multipleImages':
        return MultipleImagesPost
      default:
        return null
    }
  }


  </script>
  
  <style scoped>
  .post-card {
    @apply w-full max-w-[1021px] border-b border-gray-300;
  }
  
  .post-header {
    @apply px-12 py-2 flex items-end;
  }
  
  .posted-in {
    @apply px-1 py-0.5 rounded-xl flex items-center;
  }
  
  .post-content {
    @apply p-4 flex gap-3;
  }
  
  .post-details {
    @apply flex-1 flex flex-col;
  }
  
  .author-info {
    @apply flex justify-between items-center mb-1;
  }
  
  .author-name-time {
    @apply flex items-center gap-1 text-sm;
  }
  
  .post-text {
    @apply text-sm mb-2;
  }
  
  .post-actions {
    @apply flex items-center gap-4 mt-2;
  }
  </style>