<template>
  <div>
    <div
      @click="openModal"
      class="create-post-button flex w-full mx-auto my-2 p-4 gap-3 items-center bg-white rounded-lg shadow-md hover:bg-gray-50 transition-colors duration-300 cursor-pointer"
    >
      <div class="flex-shrink-0">
        <div
          class="w-12 h-12 rounded-full bg-cover bg-no-repeat bg-center"
          :style="{ backgroundImage: `url(${avatar})` }"
        ></div>
      </div>
      <div class="flex-grow flex items-center">
        <span class="text-xl font-medium text-gray-400">Write a post</span>
      </div>
    </div>

    <v-dialog width="1075" v-model="showModal" transition="dialog-bottom-transition">
      <v-card>
        <CreatePostModal />
      </v-card>
    </v-dialog>
  </div>
</template>

<script setup>
import { ref } from "vue";
import avatar from "~/assets/images/avatars/avatar1.png";
import CreatePostModal from "~/components/posts/CreatePostModal.vue";

const showModal = ref(false);

const openModal = () => {
  showModal.value = true;
};

const closeModal = () => {
  showModal.value = false;
};
</script>
