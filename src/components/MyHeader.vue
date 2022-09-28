<template id="header">
  <v-app>
    <v-app-bar color="secondaryMedium" light flat class="px-8 hidden-sm-and-down">
        <v-spacer></v-spacer>
        <v-tabs fixed-tabs dark color="primaryLight">
            <v-tab  active-class="active"
            @click="scroll('home')">Inicio</v-tab>
            <v-tab  active-class="active"
            @click="scroll('proyects')">Proyectos</v-tab>
            <v-tab  active-class="active"
            @click="scroll('about')">Sobre mi</v-tab>
            <v-tab  active-class="active"
            @click="scroll('contact')">Contacto</v-tab>
        </v-tabs>
    </v-app-bar>
    <Slide class="hidden-md-and-up" width="250">
        <v-tabs fixed-tabs dark color="primaryLight">
            <v-tab  active-class="active"
            @click="scroll('home')">Inicio</v-tab>
            <v-tab  active-class="active"
            @click="scroll('proyects')">Proyectos</v-tab>
            <v-tab  active-class="active"
            @click="scroll('about')">Sobre mi</v-tab>
            <v-tab  active-class="active"
            @click="scroll('contact')">Contacto</v-tab>
        </v-tabs>
    </Slide>
  </v-app>

</template>
<script>
import { Slide } from 'vue-burger-menu';

export default {
  components: {
    Slide,
  },
  name: 'MiHeader',
  methods: {
    scroll(section) {
      const s = document.getElementById(section).offsetTop;
      window.scroll({
        top: s,
        behavior: 'smooth',
      });
    },
  },
};
</script>
<style>@import '../assets/css/style.css';</style>
