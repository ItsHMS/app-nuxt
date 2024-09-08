<template>

    <v-app>
      <Toolbar />
      <Navbar />
      <LeftSidebar />
      <v-main>
        <v-container>
          <NuxtPage />
        </v-container>
      </v-main>
      <RightSidebar />
    </v-app>
</template>

<script setup>
import Toolbar from "~/components/layout/header/Toolbar.vue";
import Navbar from "~/components/layout/header/Navbar.vue";
import RightSidebar from "~/components/layout/sidebar/RightSidebar.vue";
import LeftSidebar from "~/components/layout/sidebar/LeftSidebar.vue";
</script>
