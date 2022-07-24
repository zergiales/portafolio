<template>
  <div class="contenedor3" id="contact">
    <v-row>
      <v-col cols="12" class="text-center fade-scroll d-flex justify-center">
        <h1>CONTACTA CONMIGO</h1>
        <p></p>
      </v-col>
    </v-row>
    <v-row>
      <v-col xl="6" lg="6" md="12" sm="12"
      class="text-center fade-scroll white--text d-flex justify-center
      align-center">
        <div class="contenedor1 elevation-3" height="50%">
          <h2>Si estas interesado</h2>
          <p>
            Para ponerte en contacto conmigo,hazmElo saber enviandome un correo
            electrónico<br />
            También puedes ponerte en contacto en conmigo a través de
            <strong
              ><a href="https://www.linkedin.com/in/sergio-s%C3%A1nchez-8b5711162/" class="enlace white--text">Linkedin</a
              >.</strong
            ><br />
            Y si quieres investigar más, aquí te dejo mi
            <strong
              ><a href="https://github.com/zergiales" class="enlace white--text">Github</a>.</strong
            ><br />
          </p>
        </div>
      </v-col>
      <v-col xl="6" lg="6" md="12" sm="12" class="text-center fade-scroll white--text
      d-flex justify-center align-center">
        <div class="formulario elevation-3">
          <form action=”mailto:zergiosanchezlopez@gmail.com”
          method="post" enctype="multipart/form-data">
            <!--donde metemos el nombre-->
            <v-text-field v-model="name"  :counter="20"
            :class="{error1:$v.name.$error }"
              label="Nombre" required @input="$v.name.$touch()"
              :error-messages="mensajeName()"
            ></v-text-field>
            <!--email-->
            <v-text-field
              v-model="email" label="E-mail" required :error-messages="mensajeEmail()"
            ></v-text-field>
            <!--para saber si es una empresa o particular-->
            <v-select v-model="select" :items="items"
            label="¿Eres una empresa o partcular?" required @change="$v.select.$touch()"
            @blur="$v.select.$touch()"></v-select>
            <v-checkbox v-model="checkbox"  label="Aceptas las condiciones y terminos"
            required @change="$v.checkbox.$touch()" @blur="$v.checkbox.$touch()"
            ></v-checkbox>
            <!--botones-->
            <v-btn class="mr-4" @click="submit()"
            :disabled="$v.$invalid" >Enviar</v-btn>
            <v-btn @click="clear()">Limpiar </v-btn>
          </form>
        </div>
      </v-col>
    </v-row>
  </div>
</template>
<script>
import { validationMixin } from 'vuelidate';
import {
  required, maxLength, email, helpers,
} from 'vuelidate/lib/validators';

const regexName = helpers.regex('regexName', /^[a-zA-Z]*$/);

export default {
  name: 'AboutMe',
  mixins: [validationMixin],
  validations: {
    name: {
      required, maxLength: maxLength(20), regexName,
    },
    email: { required, email },
    select: { required },
    checkbox: {
      checked(val) {
        return val;
      },
    },
  },

  data: () => ({
    name: '',
    email: '',
    select: null,
    items: [
      'Particular',
      'Empresa',
    ],
    checkbox: false,
  }),
  methods: {
    clear() {
      this.name = '';
      this.email = '';
      this.select = null;
      this.checkbox = false;
    },
    mensajeName() {
      // eslint-disable-next-line
      // debugger;
      const mensaje = [];
      if (!this.$v.name.regexName) {
        mensaje.push('el campo solo admite caracteres alfabeticos');
      } else if (!this.$v.name.required && this.$v.name.$dirty) {
        mensaje.push('rellena el campo');
      } else if (!this.$v.name.maxLength) {
        mensaje.push('has llegado al limite');
      }
      return mensaje;
    },
    mensajeEmail() {
      const mensaje = [];
      if (!this.$v.email.email) {
        mensaje.push('el campo solo admite caracteres alfabeticos');
      } else if (!this.$v.email.required && this.$v.email.$dirty) {
        mensaje.push('rellena el campo');
      }
      return mensaje;
    },
    submit() {

    },
  },

};
</script>
<style>
  .error1 {
    color: red;
  }

</style>
