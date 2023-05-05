<template>
  <v-card>
    <v-tabs v-model="tab" color="deep-purple-accent-3" align-tabs="center">
      <v-tab :value="1">Andormeda</v-tab>
      <v-tab :value="2">Teaching</v-tab>
      <v-tab :value="3">Free time</v-tab>
    </v-tabs>
    <v-window v-model="tab">
      <v-window-item v-for="n in 3" :key="n" :value="n">
        <v-container fluid>
          <v-row>
            <v-col v-for="(photo, index) in albums[n - 1].photos" :key="index" cols="12" md="4">
              <v-img :src="photo.src" :lazy-src="photo.lazySrc" aspect-ratio="1"></v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-window-item>
    </v-window>
  </v-card>
</template>
<script>
import allmight from '@/img/png/project-foto/allmight.png';
import doom from '@/img/png/project-foto/doom.jpg';
import ethan from '@/img/png/project-foto/ethan.png';

import jason from '@/img/png/project-foto/jason.jpg';
import kirby from '@/img/png/project-foto/kirby.jpg';
import nuke from '@/img/png/project-foto/nuke.jpg';

export default {
  data: () => ({
    tab: null,
    albums: [
      {
        photos: [
          {
            src: allmight,
            lazySrc: allmight,
            alt: "Picture of all might",
          },
          {
            src: doom,
            lazySrc: doom,
            alt: "Photo 2",
          },
          {
            src: ethan,
            lazySrc: ethan,
            alt: "Photo 3",
          },
          // Add more photos here...
        ],
      },
      {
        photos: [
          {
            src: jason,
            lazySrc: jason,
            alt: "Jason standing menacingly in the dar",
          },
          {
            src: kirby,
            lazySrc: kirby,
            alt: "Picture of kirby on a star",
          },
          {
            src: nuke,
            lazySrc: nuke,
            alt: "Wallpaper of a nuke",
          },
          // Add more photos here...
        ],
      },
      {
        photos: [
          {
            src: doom,
            lazySrc: doom,
            alt: "Photo 1",
          },
          {
            src: allmight,
            lazySrc: allmight,
            alt: "Picture of all might",
          },
          {
            src: ethan,
            lazySrc: ethan,
            alt: "Photo 3",
          },
          // Add more photos here...
        ],
      },
    ],
  }),
}
</script>

<style scoped>
.project-card {
  height: 100vh;
}
</style>
