<template>
  <div id="home">
    <v-row>
      <v-col xl="6" lg="6" md="12" sm="12" class="text-center fade-scroll  d-flex justify-center">
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
      <v-col xl="6" lg="6" md="12" sm="12" class="text-center fade-scroll white--text">
        <div class="contenedor1 elevation-4">
          <h1>Bienvendio a mi página web</h1>
          <h2>Soy Sergio Sánchez</h2>
          <p>
            Y Soy desarrollador de aplicaciones Web tando de la parte de back como
            de la parte de front.<br />
            Aquí podrás ver mis ultimos proyectos y ver en que tecnologías estoy especializado<br>
            Si quieres saber más pulsa en el botón
          </p>
          <v-btn color="secondaryLight" large outlined class="btnC"
            >About me</v-btn
          >
        </div>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
  name: 'MyHome',
  component: {},

};
</script>
