<template>
  <v-card class="home-card">
    <v-layout>
      <v-app-bar title="Andromeda Development">
      </v-app-bar>

      <MenuOrganism />

      <v-main class="home-main">


        <v-btn color="teal-lighten-2" @click.stop="drawer = !drawer">
          Menu
        </v-btn>
        <ProjectView />

      </v-main>
    </v-layout>
  </v-card>
</template>

<script>
import { defineComponent } from 'vue';


// Components
import ProjectView from '../Organisms/ProjectOrganism.vue';
import MenuOrganism from '../organisms/MenuOrganism.vue'

export default defineComponent({
  name: 'HomeView',

  components: {
    ProjectView,
    MenuOrganism
  },
  data() {
    return {
      drawer: null,
      items: [
        { type: 'subheader', title: 'Contact' },
        {
          title: 'Mail',
          value: 1,
          href: '/mail',
          props: {
            prependIcon: 'fa-solid fa-envelope-open-text'
          }
        },

        { type: 'divider' },
        { type: 'subheader', title: 'Socials' },
        {
          title: 'LinkedIn',
          value: 2,
          href: 'https://www.linkedin.com/in/dejorden-moerman-b669a5a2/',
          props: {
            prependIcon: 'fa-brands fa-linkedin',
          }
        },
        {
          title: 'Twitter',
          value: 3,
          href: 'https://twitter.com/DDejorden',
          props: {
            prependIcon: "fa-brands fa-twitter",
          }
        },
        {
          title: 'GitHub',
          value: 4,
          href: 'https://github.com/Dejorden94',
          props: {
            prependIcon: "fa-brands fa-github",
          }
        },
      ],
    }
  },
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
