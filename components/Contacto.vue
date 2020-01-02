<template>
<v-card-actions class="justify-center">
  <v-row align="center">
    <v-form
      class="centered_form"
      ref="form"
      v-model="valid"
    >
      <h1 class="title is-spaced" align="center">Contáctanos</h1>
      <h4 class="subtitle" align="center">Construyamos algo increíble</h4>
              <p
                class="mt-0"
              >Tu proyecto es muy importante para nosotros, contáctanos y te responderemos a la brevedad.</p>
        <br/>
      <v-text-field
        v-model="name"
        :counter="45"
        :rules="nameRules"
        label="Nombre"
        required
      ></v-text-field>

      <v-text-field
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
      ></v-text-field>

      <v-text-field
        v-model="message"
        label="Mensaje"
        placeholder= "Deja tu mensaje aquí"
        outlined
        required
      ></v-text-field>

      <v-btn
        :disabled="!valid"
        color="blue"
        class="my-2"
        @click="enviar(message, email, name)"
      >
        Enviar
      </v-btn>

      <v-btn
        color="green"
        class="mr-4"
        @click="reset"
      >
        Borrar
      </v-btn>
    </v-form>
  </v-row>
  </v-card-actions>
</template>


<script>
import axios from 'axios'

  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'El Nombre es requerido',
        v => (v && v.length <= 45) || 'El nombre debe ser menor a 45 caracteres',
      ],
      email: '',
      emailRules: [
        v => !!v || 'El E-mail es requerido',
        v => /.+@.+\..+/.test(v) || 'E-mail inválido',
      ],
      message: '',
    }),

    methods: {
      enviar (message, email, name) {
        const options = {
        method: 'post',
        url: 'https://cors-anywhere.herokuapp.com/https://api.sendgrid.com/v3/mail/send',
        data: {
              personalizations: [
                {
                  to: [
                    {
                      email: 'jmmontes@notorious.cl',
                    },
                  ],
                  subject: 'Consulta en TONSOUND de ' +  name,
                },
              ],
              from: {
                email: email,
              },
              content: [
                {
                  type: 'text/plain',
                  value: 'Nueva consulta en TONSOUND \n ' + message,
                },
              ],
        }, 
        headers: 
                  {
                    'Content-Type': 'application/json',
                    'Authorization': 'Bearer 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',
                    'Access-Control-Allow-Methods': 'POST, OPTIONS',
                    'Access-Control-Allow-Headers': 'X-Requested-With, Origin,  Content-Type, Accept',
                  },

              
      };
      axios(options);
      },
      reset () {
        this.message = ''
        this.email = ''
        this.name = ''
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
      },
    };

</script>

<style lang="scss">
  .centered_form{
    width: 50%;
    margin: 0 auto;
    @media (max-width: 680px) {
      width: 90%;
    }
  }
</style>