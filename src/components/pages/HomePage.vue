<template>
  <v-card style="min-height: 100vh;">
    <v-layout>
      <v-app-bar title="Andormeda Development">
      </v-app-bar>

      <v-navigation-drawer>
        <v-list>
          <v-list-item title="Navigation drawer"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main style="min-height: 100vh;">

      </v-main>
    </v-layout>
  </v-card>

  <ProjectView />
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
});
</script>
