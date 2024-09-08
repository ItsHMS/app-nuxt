<template>
  <v-container class="bg-white rounded-lg overflow-auto mx-auto my-0">
    <v-row class="mt-6 ml-5">
      <v-col cols="auto">
        <v-avatar size="48">
          <v-img src="~/assets/images/avatars/avatar1.png" cover></v-img>
        </v-avatar>
      </v-col>
      <v-col>
        <v-row align="center" no-gutters>
          <v-col cols="auto">
            <span class="text-lg font-medium">Abdur Rehman Malik</span>
          </v-col>
          <v-col cols="auto">
            <span class="text-lg font-medium text-gray-500"> posting in</span>
          </v-col>
          <v-col cols="auto">
            <v-menu>
              <template v-slot:activator="{ props }">
                <v-btn
                  variant="text"
                  v-bind="props"
                  class="text-lg font-medium"
                >
                  General
                  <v-icon>mdi-chevron-down</v-icon>
                </v-btn>
              </template>
            </v-menu>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

    <v-row class="mt-7 mx-20">
      <v-col>
        <p class="text-xl leading-9">
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s, when an unknown printer took a galley of type and
          scrambled it to make a type specimen book
        </p>
      </v-col>
    </v-row>

    <v-row class="mt-10 mx-20">
      <v-col>
        <v-radio-group>
          <v-radio v-for="n in 3" class="relative">
            <template v-slot:label>
              <div class="flex justify-between">
                <p>Option {{ n }}</p>
                <v-icon class="absolute right-0">mdi-trash-can-outline</v-icon>
              </div>
            </template>
          </v-radio>
        </v-radio-group>

        <v-btn
          variant="outlined"
          color="error"
          class="mt-7 w-full"
          prepend-icon="mdi-plus"
        >
          Add poll option
        </v-btn>

        <v-row class="mt-7">
          <v-col cols="6">
            <v-checkbox
              label="People can add their options"
              hide-details
            ></v-checkbox>
          </v-col>
          <v-col cols="6">
            <v-checkbox label="Allow multiple select" hide-details></v-checkbox>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

    <v-row class="mt-13 mx-17">
      <v-col v-for="image in images" :key="image" cols="3">
        <v-img
          :src="image"
          cover
          height="162"
        ></v-img>
      </v-col>
      <v-col cols="4">
        <v-sheet
          height="162"
          class="d-flex align-center justify-center border border-dashed border-gray-400"
        >
          <v-icon size="40">mdi-plus</v-icon>
        </v-sheet>
      </v-col>
    </v-row>

    <v-row class="mt-15">
      <v-col>
        <v-btn-toggle>
          <v-btn icon="mdi-format-bold"></v-btn>
          <v-btn icon="mdi-format-italic"></v-btn>
          <v-btn icon="mdi-format-underline"></v-btn>
          <v-btn icon="mdi-format-color-text"></v-btn>
          <v-btn icon="mdi-format-align-left"></v-btn>
        </v-btn-toggle>
      </v-col>
      <v-col cols="auto">
        <v-btn color="error" class="px-10">Post</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import image1 from '~/assets/images/youtubeVideo.png'
import image2 from '~/assets/images/ground.png'
const images = [image1,image2]
</script>
