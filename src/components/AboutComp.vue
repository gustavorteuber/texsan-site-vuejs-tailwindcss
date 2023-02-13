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
    colorTitle() {
      if (this.isDark == true) {
        return "text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-l from-emerald-700 via-cyan-800 to-cyan-900 md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      } else {
        return "text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-l from-emerald-700 via-cyan-800 to-cyan-900 md:text-text-4xl lg:text-7xl transition delay-150 duration-300 ease-in-out";
      }
    },
    colorSubT() {
      if (this.isDark == true) {
        return "ml-2 font-semibold text-white transition delay-150 duration-300 ease-in-out";
      } else {
        return "ml-2 font-semibold text-slate-800 transition delay-150 duration-300 ease-in-out";
      }
    },
    paragraph() {
      if (this.isDark == true) {
        return "mb-3 font-light text-gray-500 first-line:uppercase first-line:tracking-widest first-letter:text-7xl first-letter:font-bold first-letter:text-cyan-700 first-letter:mr-3 first-letter:float-left transition delay-150 duration-300 ease-in-out";
      } else {
        return "mb-3 font-light text-gray-900 first-line:uppercase first-line:tracking-widest first-letter:text-7xl first-letter:font-bold first-letter:text-gray-900 first-letter:mr-3 first-letter:float-left transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <div class="flex justify-center">
    <h1 :class="colorTitle()">
      Texsan<small :class="colorSubT()">Quem nós somos?</small>
    </h1>
  </div>
  <div class="m-5 flex justify-center">
    <p :class="paragraph()">
      Fornecedora de materiais para instalação e manutenção hidráulica,
      saneamento e infraestrutura, com produtos certificados (ABNT-NBR, DIN, ISO
      e ASTM), nosso diferencial está na capacidade de entrega rápida com
      qualidade e primando a transparência com nossos clientes.
    </p>
  </div>
</template>
