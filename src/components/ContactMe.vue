<template>
  <div class="contenedor3" id="contact">
    <v-row>
      <v-col cols="12" class="text-center fade-scroll d-flex justify-center">
        <h1>CONTACTA CONMIGO</h1>
        <p></p>
      </v-col>
    </v-row>
    <v-row>
      <v-col xl="6" lg="6" md="6" sm="12" class="text-center fade-scroll d-flex justify-center">
        <div class="contenedor4 elevation-3 white--text">
          <h2>Si estas interesado</h2>
          <p>
            Puedes ponerte en contacto conmigo por email en:
            <a
              href="mailto:zergiosanchezlopez@gmail.com"
              class="enlace white--text"
              >zegiosanchezlopez@gmail.com</a
            ><br />
            También puedes contactar conmigo a través de
            <strong
              ><a
                href="https://www.linkedin.com/in/sergio-s%C3%A1nchez-8b5711162/"
                class="enlace white--text"
                >Linkedin</a
              >.</strong
            ><br />
            Y si quieres investigar más, aquí te dejo mi
            <strong
              ><a href="https://github.com/zergiales" class="enlace white--text"
                >Github</a
              >.</strong
            ><br />
          </p>
        </div>
      </v-col>
      <v-col
        xl="6" lg="6" md="6" sm="12"
        class="text-center fade-scroll white--text d-flex justify-center align-center">
        <div class="avion">
          <lottie-player
            class="animation-reverse"
            src="https://assets1.lottiefiles.com/packages/lf20_uwos7l6e.json"
            background="transparent"
            speed="0.20"
            style="width: 100%; height: 100%"
            loop
            autoplay
          ></lottie-player>
        </div>
      </v-col>
    </v-row>
  </div>
</template>
<style>
  .avion{
    width: 300px;
    margin-top: -10%;
  }
/* estilos  que solo queremos aplicar cuando se ponga pequeño*/
@media (max-width: 768px) {
  .avion{
    margin-top: -10px;
  }
}
</style>
