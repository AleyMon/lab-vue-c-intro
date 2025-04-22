<script setup>
import { reactive } from 'vue';
import img1 from './images/USP-1.png'; // en Objeto array no me reconocia la ruta, por lo que al final se importan las imagenes en app. 
import img2 from './images/USP-2.png';
import img3 from './images/USP-3.png';

// Se declara array con diferentes propiedades para usarlo luego con v-for en div
const SectionistModulos = reactive([
  {
    id: 1,
    imagen: img1,
    descripcion: 'Truly reactive, compiler-optimized rendering system that rarely requires manual optimization.',
    titulo: 'Perfomant'
  },
  {
    id: 2,
    imagen: img2,
    descripcion: 'Builds on top of standard HTML, CSS and JavaScript with intuitive API and world-class documentation.',
    titulo: 'Approachable'
  },
  {
    id: 3,
    imagen: img3,
    descripcion: 'A rich, incrementally adoptable ecosystem that scales between a library and a full-featured framework.',
    titulo: 'Versatile'
  }
]);
</script>

<template>
  <div id="app">
    <header>
      <nav class="navegador">
        <img src="./images/Ironhack_logo.png" alt="Logo" />
        <img src="./images/Burger_menu.png" alt="Menu" />
      </nav>

      <section class="hero-text">
        <img src="./images/Vue_logo.png" alt="LogoVue" />
        <h1><strong>Welcome to Vue.js</strong></h1>
        <p>Become a coding ninja with the fastest-growing JavaScript framework</p>
        <button><strong>Awesome!</strong></button>
      </section>
    </header>

  <!--Aqui se usan los items del array. Modulo hace referencia a cada item y el punto a su propiedad-->
    <section class="sectionits">
      <div v-for="modulo in SectionistModulos" :key="modulo.id" class="modulo">
        <img :src="modulo.imagen" :alt="modulo.titulo" />
        <h2>{{ modulo.titulo }}</h2>
        <p>{{ modulo.descripcion }}</p>
      </div>
    </section>
  </div>
</template>

<style scoped>

#app {
  display: flex;
  flex-direction: column;
}
.navegador {
  display: flex;
  justify-content: space-between;
}

.hero-text {
  margin-top: 28px;
  margin-left: 72px;
  margin-right: 72px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-family: Inter;
}

.hero-text h1 {
  font-size: 40px;
  letter-spacing: -2%;
  line-height: 95px;
}

.hero-text p {
  font-size: 14px;
  line-height: 20px;
}

.hero-text button {
  background-color: #34495e;
  color: white;
  border-radius: 13px;
  width: 121px;
  height: 31px;
  margin-top: 27px;
  font-size: 14px;
}

.sectionits {
  background-color: #42b883;
  width: 600px;
  height: 312px;
  margin-top: 65px;
  display: flex;
 align-items: center;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 1rem;
}

.modulo {
  max-width: 150px;
  text-align: center;
  color: black;
}

.sectionits h2{
  font-size: 16px;
}

.sectionits p{
  font-size: 12px;
}
</style>
