<template>
  <v-app>
    <!--<v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>-->

    <!--<v-main>
      <HelloWorld/>
    </v-main>-->
    <MainBackground/>

    <section
      class="mx-auto portfolio"
    >
    <!--<v-system-bar lights-out></v-system-bar>-->
    <v-carousel
      cycle
      :continuous="true"
      :interval="interval"
      :show-arrows="true"
      hide-delimiter-background
      delimiter-icon="mdi-minus"
      height="400"
    >
      <v-carousel-item
        v-for="(slide, i) in slides"
        :key="i"
        :style="{color: activeColor}"
      >
      {{slide.urlImg}}
        <!--<v-sheet
          :color="colors[i]"
          height="100%"
          tile
        > :src="slide.src"-->

        <v-row>
          <v-btn @click="setRedirect(slide.urlLink)">Ir para o projeto</v-btn>
        </v-row>
          
        <!--</v-sheet>-->
      </v-carousel-item>
    </v-carousel>
    <!--<v-list two-line>
      <v-list-item>
      </v-list-item>
    </v-list>-->
    </section>
  </v-app>
</template>

<script>
import MainBackground from './components/MainBackground';

export default {
  name: 'App',

  components: {
    MainBackground,
  },

   data () {
      return {
        interval: 8000,
        colors: [
          'green',
          'secondary',
          'yellow darken-4',
          'red lighten-2',
          'orange darken-1',
        ],
        cycle: false,
        token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIyOTU5ODkyMTAwMDE4MCIsImp0aSI6ImUwMmI4YmUzLWJhZWQtNDdjNS1iMmI5LTgxODNjOWJkNzg5NiIsImlhdCI6IjEvMTEvMjAyMyA3OjUzOjI5IFBNIiwiaWR1c3VhcmlvIjoiMzMiLCJpZHVzdWFyaW9wYWkiOiIiLCJwZXJmaWwiOiIzIiwiaWRQZXNzb2FJNHBybyI6IjMxMjc2ODEiLCJub21lUGVyZmlsIjoiQ29ycmV0b3IiLCJub21lIjoiVk1WIENPUlJFVE9SQSBERSBTRUdVUk9TIExUREEiLCJsb2dpblVzdWFyaW8iOiIyOTU5ODkyMTAwMDE4MCIsImNvZGlnb0ZpbGlhbCI6IjEiLCJuclN1c2VwIjoiMTAyMDQ2ODkwMyIsImlkTGlzIjoiIiwicG9zc3VpQXNzZXNzb3JpYSI6IiIsIm5iZiI6MTY3MzQ2NjgwOSwiZXhwIjoxNjczNTUzMjA5LCJpc3MiOiJTb3VsSVRJc3N1ZXIiLCJhdWQiOiJTb3VsSVRBdWRpZW5jZSJ9.FQIHjm0DsQO4zGgH3kJhbZg1Zkatoa58gSApfGr0Qyg',
        slides: [
          {
            nome: 'Seguro Residencial',
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
            urlImg: './assets/img/PortalResidencial.PNG',
            urlLink: 'http://150.136.201.214/PortalResidencial/#/'
          }, 
          {
            nome: 'Seguro Vida',
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
            urlImg: './assets/img/PortalResidencial.PNG',
            //'PortalVarejo',
            urlLink: 'http://150.136.201.214/PortalVarejo/#/'
          },
          {
            nome: 'Seguro Vida Coletiva',
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
            urlImg: './assets/img/PortalResidencial.PNG',
            //'PortalVidaColetiva',
            urlLink: 'http://150.136.201.214/PortalVidaColetiva/#/'
          }
        ],
      }
    },
    methods: {
      setRedirect(link) {
        window.open(link+this.token, '_blank');
      }
    }
};
</script>

<style>
body,
ul,
li,
a {
  margin: 0;
  padding: 0;
}

a {
  text-decoration: none;
}

li {
  list-style: none;
}

.portfolio {
  width: 70%;
}
</style>