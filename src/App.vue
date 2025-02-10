<template>
  <div id="app">
    <Header/>

    <div class="container">
      <div class="custom-splide" @mouseenter="showArrows" @mouseleave="hideArrows">
        <div>
          <Splide :options="splideOptions" aria-label="Carousel com banners">
            <SplideSlide v-for="(slide, index) in slides" :key="index">
              <img :src="slide.image" :alt="`Slide ${index + 1}`" />
            </SplideSlide>
          </Splide>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
// Importando o componente


import Header from './components/layout/Header.vue';
import { Splide, SplideSlide } from '@splidejs/vue-splide'; // Importe os componentes
import '@splidejs/splide/dist/css/splide.min.css'; // Importe o CSS do Splide
import slide1 from '@/assets/img/banner 1.png';
import slide2 from '@/assets/img/banner 2.png';
import Categoria from './components/ui/Categoria.vue';



export default {
  name: 'App',
  components: {
    Header,
    Splide,
    SplideSlide,
  },data(){
    return {
      splideOptions: {
        type: 'loop', // Tipo de carrossel (loop, slide, fade)
        perPage: 1, // Número de slides visíveis
        gap: '1rem', // Espaço entre os slides
        autoplay: true, // Reprodução automática
        pauseOnHover: true,
        pagination: false,
        arrows: false, // Pausar ao passar o mouse
      },
      // Dados dos slides
      slides: [
        { image: slide1 },
        { image: slide2 },

      ],


    }

  }, methods: {
    showArrows() {
      // Ativa as setas ao entrar no hover
      this.splideOptions.arrows = true;
      // Força a atualização das opções do Splide
      this.$forceUpdate();
    },
    hideArrows() {
      // Desativa as setas ao sair do hover
      this.splideOptions.arrows = false;
      // Força a atualização das opções do Splide
      this.$forceUpdate();
    },
  },
  components:{
    Header,

  }
};
</script>

<style scoped>
/* Estilos personalizados para o carrossel */
.custom-splide {
  position: relative;
}

</style>
