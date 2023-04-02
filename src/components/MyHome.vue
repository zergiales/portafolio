<template>
  <div id="home">
    <v-row>
      <v-col xl="6" lg="6" md="6" sm="12" class="text-center fade-scroll  d-flex justify-center
      iphone">
        <div>
          <lottie-player
            class="animation-reverse"
            src="https://assets3.lottiefiles.com/packages/lf20_w51pcehl.json"
            background="transparent"
            speed="0.75"
            style="width: 100%; height: 100%"
            loop
            autoplay
          ></lottie-player>
        </div>
      </v-col>
      <v-col xl="6" lg="6" md="6" sm="12" class="text-center
      fade-scroll d-flex justify-center  white--text">
        <div class="contenedor1 elevation-3">
          <h1>Bienvendio a mi Portafolio </h1>
          <h2>Soy Sergio Sánchez</h2>
          <p>
            Soy desarrollador de aplicaciones web FullStack. <br />
            Aquí podrás ver mis últimos proyectos y los lenguajes en los que desarrollo
            actualmente<br>
            Si quieres saber más...
          </p>
          <v-btn color="secondaryLight" large outlined class="btnC"
              @click="scroll('about')">Saber más
          </v-btn
          >
        </div>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
  name: 'MyHome',
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
<style>
/* estilos  que solo queremos aplicar cuando se ponga pequeño*/
@media (max-width: 768px) {
  .iphone{
    margin-top:15% ;
  }
}
</style>
