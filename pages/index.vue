<template>
  <div>
    <CreatePostButton />
    <PostCard v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>
<script setup>
import CreatePostButton from "~/components/posts/CreatePostButton.vue";
import PostCard from "~/components/posts/PostCard.vue";
import video from "~/assets/videos/video.mp4";

const posts = ref([
  {
    id: 1111111,
    feed: "🌏 Asian food feed",
    authorName: "Mubashir Baig",
    authorUsername: "@Mubu",
    authorAvatar: "https://via.placeholder.com/48x48",
    timeAgo: "1 min",
    text: "Just signed up for the French Bakery course and OMG I've learned a lot from you.",
    commentCount: 3,
    shareCount: 16,
    likeCount: 0,
    contentType: "text",
  },
  {
  id: 345353,
  feed: "👋🏼 Feed",
  authorName: "Enmanuel Betances",
  authorUsername: "@betances",
  authorAvatar: "https://via.placeholder.com/48x48",
  isVerified: true,
  timeAgo: "5 min",
  text: "WOW @abdurMalik What a recipe!",
  contentType: "image",
  content: {
    type: "image",
    url: "https://via.placeholder.com/929x283",
    alt: "Recipe image" 
  },
  mentionedUsers: ["@abdurMalik"],
  commentCount: 3,
  shareCount: 16
},
  {
    id: 4523451,
    feed: "🌏 Asian food feed",
    authorName: "Mubashir Baig",
    authorUsername: "@Mubu",
    authorAvatar: "https://via.placeholder.com/48x48",
    timeAgo: "1 min",
    text: "Just signed up for the French Bakery course and OMG I've learned a lot from you.",
    contentType: "video",
    content: {
      type: "video",
      url: video,
      poster:
        "https://images.pexels.com/videos/6172664/pexels-photo-6172664.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
    },
    commentCount: 3,
    shareCount: 16,
  },
  {
    id: 98741,
    feed: "🌏 Food Rating",
    authorName: "Foodie Critic",
    authorUsername: "@foodcritic",
    authorAvatar: "https://via.placeholder.com/48x48",
    timeAgo: "2 hours",
    text: "Just tried this amazing dish at the new restaurant downtown!",
    contentType: "imageRating",
    content: {
      imageUrl: "https://via.placeholder.com/929x283",
      imageAlt: "Delicious gourmet dish",
      rating: 4,
    },
    commentCount: 12,
    shareCount: 5,
  },
  {
    id: 234521,
    feed: "📸 Photo Gallery",
    authorName: "Photography Enthusiast",
    authorUsername: "@photogeek",
    authorAvatar: "https://via.placeholder.com/48x48",
    timeAgo: "3 hours",
    text: "Check out these amazing shots from my recent trip!",
    contentType: "multipleImages",
    content: {
      rows: [
        [
          {
            url: "https://via.placeholder.com/480x283",
            alt: "Scenic landscape",
            active: true,
          },
          {
            url: "https://via.placeholder.com/310x283",
            alt: "City skyline",
            active: false,
          },
        ],
        [
          {
            url: "https://via.placeholder.com/480x283",
            alt: "Mountain view",
            active: false,
          },
          {
            url: "https://via.placeholder.com/310x283",
            alt: "Beach sunset",
            active: false,
          },
        ],
      ],
    },
    commentCount: 25,
    shareCount: 10,
  },
  {
    id: 123424,
    feed: "🎫 Event Announcement",
    authorName: "Event Organizer",
    authorUsername: "@eventplanner",
    authorAvatar: "https://via.placeholder.com/48x48",
    timeAgo: "1 day",
    text: "Don't miss out on this amazing event!",
    contentType: "eventBanner",
    content: {
      date: new Date("2024-01-05T14:30:00"),
      title: "Live cooking show with Rehana Malik",
    },
    commentCount: 50,
    shareCount: 30,
  },
]);
</script>
<script>
export default {
  name: "IndexPage",
};
</script>
