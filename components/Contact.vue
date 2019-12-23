<template>
  <section id="contact"  class="section is-medium" style="background-color: rgba(245, 245, 245, 1)">
    <div class="container has-text-centered"  align="center" fluid style="padding: 30%; width: 100%">
      <h1 class="title is-spaced">Contáctanos</h1>
      <h4 class="subtitle">Construyamos algo increible</h4>
              <p
                class="mt-0"
              >Tu proyecto es muy importante para nosotros, contactanos y te responderemos a la brevedad.</p>

      <form action="https://formspree.io/pulsar.dev.team@gmail.com" method="POST">
        <div class="field">
          <label class="label" for="name">Nombre</label>
          <div class="control">
            <input v-validate="'required'" v-model="name" class="input" :class="{ 'is-danger': errors.has('name') }" id="name" name="name" type="text" placeholder="Nombre" required>
          </div>
          <span v-show="errors.has('name')" class="help is-danger">{{ errors.first('name') }}</span>
        </div>

        <div class="field">
          <label class="label" for="email">Email</label>
          <div class="control has-icons-left has-icons-right">
            <input v-validate="'required|email'" v-model="email" class="input" :class="{ 'is-danger': errors.has('email') }" id="email" name="email" type="text" placeholder="Email" required>
            <span class="icon is-small is-left has-text-grey"><i class="fa fa-envelope"></i></span>
            <span v-show="errors.has('email')" class="icon is-small is-right has-text-grey"><i class="fa fa-warning"></i></span>
          </div>
          <span v-show="errors.has('email')" class="help is-danger">{{ errors.first('email') }}</span>
        </div>

        <div class="field">
          <label class="label" for="message">Mensaje</label>
          <div class="control">
            <textarea v-validate="'required'" v-model="message" class="textarea" :class="{ 'is-danger': errors.has('message') }" id="message" name="message" placeholder="Mensaje" required></textarea>
          </div>
          <span v-show="errors.has('message')" class="help is-danger">{{ errors.first('message') }}</span>
        </div>

        <div class="field is-grouped">
          <div class="control">
            <input type="submit" class="button is-primary" value="Enviar">
          </div>
          <div class="control">
            <button class="button is-light" @click="cancel">Cancelar</button>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
  export default {
    $_veeValidate: {
      validator: 'new'
    },
    name: 'contact',
    data () {
      return {
        name: '',
        email: '',
        message: ''
      }
    },
    methods: {
      cancel () {
        this.name = ''
        this.email = ''
        this.message = ''
      }
    }
  }
</script>

<style lang="scss" scoped>
  .input, .textarea {
    background-color: #363636;
    color: #dbdbdb;
  }

  .input:not(.is-danger), .textarea:not(.is-danger) {
    border: none;
  }

  .label {
    color: #b5b5b5;
  }
</style>
