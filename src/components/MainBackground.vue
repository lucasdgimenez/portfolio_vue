<template>
  <section class="fullBackground">
      <h2 class="titulo_main">Lucas Dias</h2>
      <h3 class="sub_titulo">Front End</h3>
      <nav class="menu_main">
        <ul class="first">
          <li><a href="#port" @click="teste">Portfolio</a></li>
          <li><a href="https://wa.me/5511985974862">Contato</a></li>
        
        </ul>
        <ul class="second">
            <li><a href="https://www.linkedin.com/in/lucasdgimenez/" target="_blanket">Linkedin</a></li>
            <li><a href="https://github.com/lucasdgimenez" target="_blanket">GitHub</a></li>
        </ul>
      </nav>
      
        
    </section>
</template>

<script>
export default {
    methods: {
        teste() {
            window.scroll({
                top: 500,
                behavior: 'smooth'
            });
        }
    }
}
</script>

<style scoped>
.fullBackground {
    background-color: aqua;
    background-position: center;
    background-size: cover;
    background-image: url('../assets/img/foto1.webp');
    /*position: absolute;

    top: 0;
    left: 0;*/
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    color: white;
}

.menu_main {
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin-top: 400px;
}

.menu_main ul {
  display: flex;
  justify-content: center;
}

.menu_main a {
  color: white;
  background-color: #00448B;
  padding: 15px;
}

.menu_main ul.second {
  margin: 60px 0 0 0;
}

.menu_main a:hover {
  background-color: #090e53;
  transition: 0.8s ease-out;
}

.menu_main li,
.second_menu li {
  margin: 0 8px;
}

.titulo_main,
.sub_titulo {
  text-transform: uppercase;
  position: absolute;
}

.titulo_section {
  text-transform: uppercase;
  text-align: center;
}

.titulo_main,
.titulo_section {
  font-size: 30pt;
}

.titulo_main {
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.sub_titulo {
  font-size: 25pt;
  top: 32%;
  left: 42%;
}

</style>