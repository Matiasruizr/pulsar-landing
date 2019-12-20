<template>
  <section id="team" class="hero is-medium" style="background-color: whitesmoke">
    <div class="hero-body">
      <div class="container has-text-centered">
        <h1 class="title is-spaced">El Equipo</h1>

        <div class="columns">
          <div class="column">
            <team-person :person="persons[0]"></team-person>
          </div>
          <div class="column">
            <team-person :person="persons[1]"></team-person>
          </div>
          <div class="column">
            <team-person :person="persons[2]"></team-person>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  import TeamPerson from './TeamPerson.vue'

  export default {
    name: 'team',
    components: {
      TeamPerson
    },
    data () {
      return {
        persons: [
          {
            id: '',
            name: 'Área Técnica',
            avatar: '',
            image: '/images/team/bielsa.jpg',
            description: '<em>10 Integrantes</em>',
            skills: [ 'JavaScript', 'Vue.js', 'Angular.js', 'Node.js', 'React','PHP', 'BI','Ruby', 'Python', 'AWS', 'SQL', 'NoSQL'],
            link: ''
          },
          {
            id: '',
            name: 'Área Proyectos',
            avatar: '',
            image: '/images/team/El-lobo-de-wall-street3-1024x682.jpg',
            description: '<em>3 Integrantes</em>',
            skills: ['Mktg Digital', 'Ecommerce', 'Planning','Vue.js', 'JavaScript', 'Angular.js', 'Python', 'Node.js'],
            link: ''
          },
          {
            id: '',
            name: 'Especialidades',
            avatar: '',
            image: '/images/team/monos.jpg',
            description: '<em>3 Integrantes</em>',
            skills: ['Big data', 'Econometría', 'estadística', 'BI'],
            link: ''
          }
        ]
      }
    },
    mounted () {
      this.persons.sort(() => { return 0.5 - Math.random() })
    }
  }
</script>
