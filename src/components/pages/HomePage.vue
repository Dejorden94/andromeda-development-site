<template>
  <v-card class="home-card">
    <v-layout>
      <v-app-bar title=" Andormeda Development">
      </v-app-bar>

      <v-navigation-drawer>
        <v-list>
          <v-list-item title="Navigation">
            <v-card class="mx-auto" max-width="300">
              <v-list :items="items"></v-list>
            </v-card>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main class="home-main">
        <ProjectView />
      </v-main>
    </v-layout>
  </v-card>
</template>

<script>
import { defineComponent } from 'vue';

// Components
import ProjectView from '../Organisms/ProjectOrganism.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    ProjectView,
  },
  data: () => ({
    items: [
      { type: 'subheader', title: 'Contact' },
      {
        title: 'Contact me',
        value: 1,
      },
      {
        title: 'Item #2',
        value: 2,
      },
      {
        title: 'Item #3',
        value: 3,
      },
      { type: 'divider' },
      { type: 'subheader', title: 'Socials' },
      {
        title: 'Item #4',
        value: 4,
      },
      {
        title: 'Item #5',
        value: 5,
      },
    ],
  }),

});
</script>

<style scoped>
.home-card {
  min-height: 100vh;
}

.home-main {
  min-height: 100vh;
}
</style>
