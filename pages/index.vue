<template>
  <div>
    <navbar-top></navbar-top>

    <hero-index></hero-index>

    <projects-showcase></projects-showcase>

    <team></team>

    <!-- <contact></contact> -->

    <contacto></contacto>


    <footer class="footer" style="background-color: hsl(0, 0%, 8%)">
      <div class="container has-text-grey">
        <div class="content has-text-centered">
          <p>
            <strong class="has-text-grey">TONSOUND</strong> es un grupo de  <a href="#team" v-smooth-scroll>desarrolladores</a>.
            Nuestros proyectos son hechos con cuidado y detalle.
            <br>
            <!-- If you love what we do, please consider <a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=38BCHG4HYDWH8" title="Donate">donating</a>. -->
          </p>
          <!-- <p>
            <a class="icon" href="https://github.com/pulsardev" title="GitHub">
              <i class="fa fa-github"></i>
            </a>
          </p> -->
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
  import NavbarTop from '~/components/NavbarTop.vue'
  import HeroIndex from '~/components/HeroIndex.vue'
  import ProjectsShowcase from '~/components/ProjectsShowcase.vue'
  import Team from '~/components/Team.vue'
  import Contact from '~/components/Contact.vue'
  import Contacto from '~/components/Contacto.vue'


  export default {
    components: {
      NavbarTop,
      HeroIndex,
      ProjectsShowcase,
      Team,
      Contact,
      Contacto,

    }
  }
</script>
