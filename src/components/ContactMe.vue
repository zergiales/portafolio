<template>
  <div class="contenedor3" id="contact">
    <v-row>
      <v-col cols="12" class="text-center fade-scroll d-flex justify-center">
        <h1>CONTACT WITH ME</h1>
        <p></p>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="6" class="text-center fade-scroll white--text d-flex justify-center
      align-center">
        <div class="contenedor1 elevation-3" height="50%">
          <h2>Si estas interesado</h2>
          <p>
            Para ponerte en contacto conmigo,hazemlo saber enviandome un correo
            electronico<br />
            Tambien puedes ponerte en contacto en conmigo a traves de
            <strong
              ><a href="https://www.linkedin.com/in/sergio-s%C3%A1nchez-8b5711162/" class="enlace white--text">Linkedin</a
              >.</strong
            ><br />
            Y si aun no has visto mis proyectos te recomiendos que mirar mi
            <strong
              ><a href="https://github.com/zergiales" class="enlace white--text">Github</a>.</strong
            ><br />
          </p>
        </div>
      </v-col>
      <v-col cols="6" class="text-center fade-scroll white--text
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
            <v-checkbox v-model="checkbox"  label="Do you agree?"
            required @change="$v.checkbox.$touch()" @blur="$v.checkbox.$touch()"
            ></v-checkbox>
            <!--botones-->
            <v-btn class="mr-4" @click="submit()"
            :disabled="$v.$invalid" >Enviar</v-btn>
            <v-btn @click="limpiar()">Limpiar </v-btn>
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
  updated() {
    // eslint-disable-next-line
    console.log(this.$v);
  },
  mounted() {
    // eslint-disable-next-line
    console.log(this.$v);
  },
  methods: {
    clear() {
      this.$v.$reset();
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
      return console.log(`nombre: ${this.name}
      correo: ${this.email}
      email: ${this.select}`);
    },
  },

};
</script>
<style>
  .error1 {
    color: red;
  }

</style>
