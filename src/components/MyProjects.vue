<template>
  <div>
    <v-row>
      <v-col cols="12" class="text-center fade-scroll  d-flex justify-center">
        <h1>PROYECTS</h1>
        <p></p>
      </v-col>
    </v-row>
    <!--tarjetas donde se muestran todos los proyectos que tengo-->
    <v-row>
      <v-col v-for="proyect in proyects" :key="proyect.name"
      cols="3" class="text-center fade-scroll  d-flex justify-center">
        <v-card class="mx-auto my-12" width="350" height="450">
          <!--si ponemos imagenes poner height="450"-->
          <template slot="progress">
            <v-progress-linear color="deep-purple" height="10" indeterminate></v-progress-linear>
          </template>
          <!-- <v-img height="250" :src="proyect"></v-img> -->
          <!-- <v-img src="../assets/img/logos/html5.png" height="250"></v-img> -->
          <v-card-title>{{ proyect.name}}</v-card-title>
          <v-img v-bind="proyects.img"></v-img>
          <v-card-text class="text-justify">
            <div height="500">{{proyect.descripcion}}</div>
          </v-card-text>
          <v-divider class="mx-4"></v-divider>
          <v-card-actions>
            <v-btn color="primary" large outlined class="btnC">
              Show more
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
      image: {
        src: 'https://lenguajejs.com/javascript/logo.svg',
        alt: 'Logo de Javascript',
      },
      proyects: [
        {
          img: '../assets/img/capturas/ahorcado.png',
          name: 'Ahorcado',
          tecnologias: 'css ,javascript y html',
          descripcion: 'ahorcado que realizado con un array que contiene palabras que tendras que adivinar',
          link: 'hhh',
        },
        {
          img: '',
          name: 'Trivial',
          tecnologias: 'php csv javascript css y html',
          descripcion: 'trivial que guarda las preguntas en un csv.100% funcional',
          link: '',
        },
        {
          img: '../assets/img/capturas/calculadora.png',
          name: 'calculadora',
          tecnologias: 'javascript css y html ',
          descripcion: 'calculadora realizada con el pardigma poo. tiene opcion cientifica',
          link: '',
        },
        {
          img: '../assets/img/capturas/gestorBD.png',
          name: 'gestor de alumnos',
          tecnologias: 'php bootstrap css html y javascript',
          descripcion: 'gestor de base de datos de una escula de alumnos funcional',
          link: '',
        },
      ],
    };
  },
  methods: {
  },
};
</script>
