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
          <v-list-item prepend-icon="fa-solid fa-house" title="Home" value="project" @click="toggleOrganisms('project')"
            :disabled="clicked === 'project'"></v-list-item>
          <v-list-item prepend-icon="fa-solid fa-address-card" title="About" value="about"
            @click="toggleOrganisms('about')" :disabled="clicked === 'about'"></v-list-item>

        </v-list>



        <v-list density="compact" nav>
          <v-list-item prepend-icon="fa-brands fa-linkedin" title="Linkdin" value="linkdin"
            href="https://www.linkedin.com/in/dejorden-moerman-b669a5a2/" target="_blank"></v-list-item>
          <v-list-item prepend-icon="fa-brands fa-github-alt" title="GitHub" value="github"
            href="https://github.com/Dejorden94" target="_blank"></v-list-item>
          <v-list-item prepend-icon="fa-brands fa-twitter" title="Twitter" value="twitter"
            href="https://twitter.com/DDejorden" target="_blank"></v-list-item>
        </v-list>



        <v-list density="compact" nav>
          <v-list-item prepend-icon="fa-solid fa-envelope" title="Mail me!" value="home"></v-list-item>
        </v-list>

      </v-navigation-drawer>


      <v-main class="home-main">

        <ProjectView v-show="showProject" />
        <AboutOrganism v-show="showAbout" />
      </v-main>
    </v-layout>
  </v-card>
</template>

<script>
import { defineComponent } from 'vue';


// Components
import ProjectView from '../Organisms/ProjectOrganism.vue';
import MenuOrganism from '../organisms/MenuOrganism.vue';
import AboutOrganism from '../organisms/AboutOrganism.vue';


export default defineComponent({
  name: 'HomeView',

  components: {
    ProjectView,
    MenuOrganism,
    AboutOrganism
  },
  data() {
    return {
      drawer: true,
      rail: true,
      showProject: true,
      showAbout: false,
      clicked: null
    }
  },
  methods: {
    toggleOrganisms(clicked) {
      if (clicked === 'about' && this.showAbout === false && this.showProject === true) {
        this.showAbout = true;
        this.showProject = false;
        this.clicked = 'about';
      } else if (clicked === 'project' && this.showAbout === true && this.showProject === false) {
        this.showAbout = false;
        this.showProject = true;
        this.clicked = 'project';
      }
    },

  }
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
