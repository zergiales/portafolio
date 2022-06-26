<template id="header">
  <v-app-bar color="secondaryMedium" light flat class="px-8 hidden-sm-and-down">
        <v-spacer></v-spacer>
        <v-tabs fixed-tabs dark color="primaryLight">
            <v-tab  active-class="active"
            @click="scroll('home')">Inicio</v-tab>
            <v-tab  active-class="active"
            @click="scroll('proyects')">Proyectos</v-tab>
            <v-tab  active-class="active"
            @click="scroll('about')">SOBRE MÍ</v-tab>
            <v-tab  active-class="active"
            @click="scroll('contact')">Contacto</v-tab>
        </v-tabs>
  </v-app-bar>
</template>
<script>
export default {
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
