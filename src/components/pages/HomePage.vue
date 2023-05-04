<template>
  <v-card class="home-card">
    <v-layout>
      <v-app-bar title="Andromeda Development">
      </v-app-bar>

      <v-navigation-drawer v-model="drawer" :rail="rail" permanent @click="rail = false">
        <v-list-item
          prepend-avatar="https://media.licdn.com/dms/image/C4E03AQEySEj0BpD0aA/profile-displayphoto-shrink_800_800/0/1610970734616?e=1688601600&v=beta&t=a2r7uTn2GavY4mONCJIKf042jWqSdGYr2AxDwJccrQk"
          title="Dejorden Moerman" nav>
          <template v-slot:append>
            <v-btn variant="text" icon="fa-solid fa-chevron-left" @click.stop="rail = !rail"></v-btn>
          </template>
        </v-list-item>

        <v-divider></v-divider>


        <v-list density="compact" nav>
          <v-list-item prepend-icon="fa-solid fa-house" title="Home" value="home"></v-list-item>
          <v-list-item prepend-icon="fa-solid fa-address-card" title="About" value="about"></v-list-item>
        </v-list>



        <v-list density="compact" nav>
          <v-list-item prepend-icon="fa-brands fa-linkedin" title="Linkdin" svalue="linkdin"
            href="https://www.linkedin.com/in/dejorden-moerman-b669a5a2/"></v-list-item>
          <v-list-item prepend-icon="fa-brands fa-github-alt" title="GitHub" value="github"
            href="https://github.com/Dejorden94"></v-list-item>
          <v-list-item prepend-icon="fa-brands fa-twitter" title="Twitter" value="twitter"
            href="https://twitter.com/DDejorden"></v-list-item>
        </v-list>



        <v-list density="compact" nav>
          <v-list-item prepend-icon="fa-solid fa-envelope" title="Mail me!" value="home"></v-list-item>
        </v-list>

      </v-navigation-drawer>


      <v-main class="home-main">
        <!-- <MenuOrganism /> -->

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
      drawer: true,
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
      rail: true,
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
