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
      
      height="400"
    >
    <!--hide-delimiter-background
      delimiter-icon="mdi-minus"-->
      <v-carousel-item
        v-for="(slide, i) in slides"
        :key="i"
        :src="slide.src"
        @click="setModal(slide)"
      >
      {{slide.urlImg}}
          
      </v-carousel-item>
    </v-carousel>
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          {{selectProject.name}}
        </v-card-title>

        <v-card-text>
          {{selectProject.description}}
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
           <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            Fechar
          </v-btn>
          <v-btn
            color="primary"
            text
            @click="setRedirect(selectProject.url)" 
          >
            Ir para o projeto
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--<v-list two-line>
      <v-list-item>
      </v-list-item>
    </v-list>-->
    </section>
    <footer>
      <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css">
       <a href="https://wa.me/5511985974862" style="position:fixed;width:60px;height:60px;bottom:40px;right:40px;background-color:#25d366;color:#FFF;border-radius:50px;text-align:center;font-size:30px;box-shadow: 1px 1px 2px #888;
      z-index:1000;" target="_blank">
        <i style="margin-top:16px" class="fa fa-whatsapp"></i>
      </a>
    </footer>
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
        selectProject: {},
        cycle: false,
        dialog: false,
        token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIyOTU5ODkyMTAwMDE4MCIsImp0aSI6ImUwMmI4YmUzLWJhZWQtNDdjNS1iMmI5LTgxODNjOWJkNzg5NiIsImlhdCI6IjEvMTEvMjAyMyA3OjUzOjI5IFBNIiwiaWR1c3VhcmlvIjoiMzMiLCJpZHVzdWFyaW9wYWkiOiIiLCJwZXJmaWwiOiIzIiwiaWRQZXNzb2FJNHBybyI6IjMxMjc2ODEiLCJub21lUGVyZmlsIjoiQ29ycmV0b3IiLCJub21lIjoiVk1WIENPUlJFVE9SQSBERSBTRUdVUk9TIExUREEiLCJsb2dpblVzdWFyaW8iOiIyOTU5ODkyMTAwMDE4MCIsImNvZGlnb0ZpbGlhbCI6IjEiLCJuclN1c2VwIjoiMTAyMDQ2ODkwMyIsImlkTGlzIjoiIiwicG9zc3VpQXNzZXNzb3JpYSI6IiIsIm5iZiI6MTY3MzQ2NjgwOSwiZXhwIjoxNjczNTUzMjA5LCJpc3MiOiJTb3VsSVRJc3N1ZXIiLCJhdWQiOiJTb3VsSVRBdWRpZW5jZSJ9.FQIHjm0DsQO4zGgH3kJhbZg1Zkatoa58gSApfGr0Qyg',
        slides: [
          {
            nome: 'Seguro Residencial',
            description: 'Compra de seguro residencial',
            src: 'https://testeportfolio.vercel.app/images/PortalResidencial.PNG',
            urlLink: 'http://150.136.201.214/PortalResidencial/#/'
          }, 
          {
            nome: 'Seguro Vida',
            description: 'Compra de seguro de vida',
            src: 'https://testeportfolio.vercel.app/images/PortalVarejo.PNG',
            urlLink: 'http://150.136.201.214/PortalVarejo/#/'
          },
          {
            nome: 'Seguro Vida Coletiva',
            description: 'Gerador de pdf de apolice ',
            src: 'https://testeportfolio.vercel.app/images/PortalVidaColetiva.PNG',
            urlLink: 'http://150.136.201.214/PortalVidaColetiva/#/'
          }
        ],
      }
    },
    methods: {
      setRedirect(link) {
        window.open(link+this.token, '_blank');
      },
      setModal(project) {
        
        this.dialog = true
        this.selectProject.name = project.nome
        this.selectProject.description = project.description
        this.selectProject.url = project.urlLink
        console.log("selectProject: ", this.selectProject)
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