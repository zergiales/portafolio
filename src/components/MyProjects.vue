<template>
  <div id="proyects">
    <v-row>
      <v-col col="12" class="text-center fade-scroll  d-flex justify-center">
        <h1>PROYECTOS</h1>
        <p></p>
      </v-col>
    </v-row>
    <!--tarjetas donde se muestran todos los proyectos que tengo-->
    <v-row>
      <v-col v-for="proyect in proyects" :key="proyect.name"
      xl="3" lg="4" md="6" sm="12" class="text-center fade-scroll tarjeta d-flex justify-center">
        <v-card class="mx-auto my-12" width="350" height="580">
          <template slot="progress">
            <v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
          </template>
          <v-card-title class="d-flex justify-center align-center">
            <strong class="titulillo display-1">{{ proyect.name}}</strong></v-card-title>
          <v-img  contain :src="getImg(proyect.img)" :class="proyect.img" class="imagen"></v-img>
          <div class="d-flex flex-row mb-6">
            <v-img contain v-for="icon in proyect.tecnologias"
            :key="icon.tecnologias" :src="getImg(icon)" class="iconitos" ></v-img>
          </div>
          <v-card-text class="text-justify">
            <div height="500" class="texto">{{proyect.descripcion}}</div>
          </v-card-text>
          <v-divider class="mx-4"></v-divider>
          <v-card-actions class="d-flex justify-center align-center">
            <v-btn color="primary" large outlined class="btnC" @click="abrirVentana(proyect.link1)">
              Repo
            </v-btn>
            <v-btn color="primary" large outlined class="btnC" v-bind:disabled="!proyect.link2"
            @click="abrirVentana(proyect.link2)">
              Demo
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
  name: 'MyProjects',
  data() {
    return {
      proyects: [
        {
          img: 'capturas/geo',
          name: 'Geo Water',
          tecnologias: [
            'logos/logo',
            'logos/vuetify',
            'logos/slim',
            'logos/vuex',
            'logos/axios',
          ],
          descripcion: 'Aplicacion de geoposicionamiento y localización de baños',
          link1: 'https://github.com/zergiales/geo-water.git',
          link2: '',
        },
        {
          img: 'capturas/brick',
          name: 'Brick Game',
          tecnologias: [
            'logos/html5',
            'logos/css3',
            'logos/javascript',
          ],
          descripcion: 'brick breaker sencillo  (juego arcade)',
          link1: 'https://github.com/zergiales/brick-game.git',
          link2: 'https://brick-game-zs.netlify.app/',
        },
        {
          img: 'capturas/ahorcadoIcon',
          name: 'Ahorcado',
          tecnologias: [
            'logos/html5',
            'logos/css3',
            'logos/javascript',
          ],
          descripcion: 'Ahorcado que realizado con un array  que tiene palabras (POO)',
          link1: 'https://github.com/zergiales/ahorcado.git',
          link2: 'https://6429c2adab8bc433a83e3ed0--ahorcate.netlify.app/',
        },
        {
          img: 'capturas/trivialIcon',
          name: 'Trivial',
          tecnologias: [
            'logos/html5',
            'logos/css3',
            'logos/javascript',
            'logos/php',
            'logos/csv',
          ],
          descripcion: 'Trivial que guarda las preguntas en un csv. 100% funcional.',
          link1: 'https://github.com/zergiales/trivial.git',
          link2: '',
        },
        {
          img: 'capturas/calculadoraIcon',
          name: 'Calculadora',
          tecnologias: [
            'logos/html5',
            'logos/css3',
            'logos/javascript',
          ],
          descripcion: 'Calculadora realizada con el paradigma poo. tiene opcion cientifica. (POO)',
          link1: 'https://github.com/zergiales/calculadora.git',
          link2: '',

        },
        {
          img: 'capturas/gesto',
          name: 'Gestor alumnos',
          tecnologias: [
            'logos/html5',
            'logos/bootstrap',
            'logos/javascript',
            'logos/php',
            'logos/sql',
          ],
          descripcion: 'Gestor de base de datos de una escuela de alumnos funcional.',
          link1: 'https://github.com/zergiales/gestor-base-alumnos.git',
          link2: '',
        },
      ],
    };
  },
  methods: {
    getImg(img) {
      // eslint-disable-next-line
      return require(`../assets/img/${img}.png`);
    },
    abrirVentana(parametro) {
      window.open(parametro);
    },
  },
};
</script>
