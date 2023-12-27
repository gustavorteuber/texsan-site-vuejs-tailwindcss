<script>
import { useDark, useToggle } from "@vueuse/core";
export default {
  setup() {
    const isDark = useDark();
    const toggle = useToggle(isDark);
    return {
      isDark,
      toggle,
    };
  },
  methods: {
    colorText() {
      if (this.isDark == false) {
        return "mb-5 text-6xl font-extrabold leading-none tracking-tight text-white md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      } else {
        return "mb-5 text-6xl font-extrabold text-slate-800 md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      }
    },
    colorButton() {
      if (this.isDark == false) {
        return "m-10 inline-flex items-center justify-center px-5 py-3 text-base font-extrabold text-center text-slate-800 bg-gradient-to-l from-emerald-700 via-cyan-800 to-indigo-900 rounded-lg transition delay-150 duration-300 ease-in-out";
      } else {
        return "m-10 inline-flex items-center justify-center px-5 py-3 text-base font-extrabold text-center text-white bg-gradient-to-l from-emerald-700 via-cyan-800 to-indigo-900 rounded-lg transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <div class="all">
    <div class="flex justify-center">
      <h1
        class="mb-4 text-7xl font-extrabold leading-none tracking-tight text-transparent bg-clip-text bg-gradient-to-l from-emerald-700 via-cyan-800 to-indigo-900 md:text-text-4xl lg:text-7xl">
        O site da Texsan
        <div class="flex justify-center">
          <h1 :class="colorText()">está chegando</h1>
        </div>
      </h1>
    </div>
    <div class="flex justify-center">
      <p class="mb-6 text-lg font-normal text-gray-500 lg:text-xl sm:px-16 xl:px-48">
        A Texsan Saneamentos destaca-se como referência no mercado de fornecimento de materiais para manutenções
        hidráulicas, oferecendo produtos de alta qualidade que atendem às demandas mais exigentes. Nosso compromisso com a
        excelência reflete-se não apenas na durabilidade e eficiência de nossos produtos, mas também na agilidade
        excepcional de nossas entregas. Priorizamos a satisfação do cliente, proporcionando um serviço eficaz e pontual,
        garantindo que nossos clientes recebam seus materiais no prazo estabelecido. Conte conosco para suprir suas
        necessidades hidráulicas com confiança e eficiência, pois na Texsan, a qualidade e a rapidez caminham juntas.
      </p>
    </div>
    <div class="flex justify-center">
      <a href="https://wa.me/5547992877667" target="_blank" :class="colorButton()">
        Saiba mais
        <svg class="w-5 h-5 ml-2 -mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd"
            d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
            clip-rule="evenodd"></path>
        </svg>
      </a>
    </div>
  </div>
</template>

<style scoped>
.all {
  padding: 1rem;
}
</style>
