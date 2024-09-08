<template>
  <v-system-bar color="#191a1a" height="80" app>
    <v-row no-gutters align="center">
      <v-col cols="3">
        <div
          class="rounded-lg text-white font-bold text-lg flex items-center max-w-fit gap-5 bg-[#565656] p-2"
        >
          <v-avatar size="35" rounded="sm" color="white">
            <v-img :src="logo" cover />
          </v-avatar>
          Rani Desi Market
        </div>
      </v-col>

      <v-col cols="5">
        <v-text-field
          bg-color="#565656"
          hide-details
          prepend-inner-icon="mdi-magnify"
          variant="solo"
        ></v-text-field>
      </v-col>

      <v-col cols="4" class="d-flex justify-end align-center">
        <v-btn icon rounded color="#565656" class="mr-2">
          <v-icon>mdi-bell</v-icon>
        </v-btn>
        <v-btn icon rounded color="#565656" class="mr-4">
          <v-icon>mdi-message</v-icon>
        </v-btn>

        <v-menu>
          <template v-slot:activator="{ props }">
            <div v-bind="props" class="text-white pa-0 cursor-pointer">
              <div class="d-flex align-center">
                <v-avatar size="50" class="mr-4">
                  <v-img :src="avatar1" cover />
                </v-avatar>
                <div class="text-left mr-4">
                  <div class="text-body-1 font-weight-bold">Abdur Malik</div>
                  <div class="text-caption">Member</div>
                </div>
                <v-icon icon="mdi-chevron-down"></v-icon>
              </div>
            </div>
          </template>
          <v-list>
            <v-list-item>
              <v-list-item-title>Profile</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Settings</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Logout</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-col>
    </v-row>
  </v-system-bar>
</template>

<script setup>
import logo from '../../../assets/images/logo.png'
import avatar1 from '../../../assets/images/avatars/avatar1.png'
</script>
