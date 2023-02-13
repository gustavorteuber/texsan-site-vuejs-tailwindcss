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
    colorFooter() {
      if (this.isDark == true) {
        return "flex justify-between bg-neutral-900 text-white w-screen transition delay-150 duration-300 ease-in-out";
      } else {
        return "flex justify-between bg-white text-gray-900 w-screen transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <nav :class="colorFooter()">
    <div class="px-5 xl:px-12 py-6 flex w-full items-center">
      <img class="w-20" src="../assets/texsantransparent.png" alt="" />
      <ul
        class="hidden md:flex px-4 mx-auto font-semibold font-heading space-x-12"
      >
        <li><a class="hover:text-gray-500" href="/">Home</a></li>
        <li>
          <RouterLink class="hover:text-gray-500" to="/sobrenos"
            >Sobre nós
          </RouterLink>
        </li>
        <li>
          <a
            class="hover:text-gray-5 00"
            href="mailto:texsan@texsan.com.br"
            target="_blank"
            >Entre em contato</a
          >
        </li>
      </ul>
      <div class="hidden xl:flex items-center space-x-5 items-center">
        <button
          v-if="isDark == true"
          type="button"
          @click="isDark = !isDark"
          class="block py-2 pl-3 pr-4 text-neutral-700 rounded hover:bg-neutral-100 md:hover:bg-transparent md:hover:text-yellow-700 md:p-0 :text-neutral-400 md::hover:text-yellow-500 :hover:bg-neutral-700 :hover:text-gray-500 md::hover:bg-transparent :border-cyan-700"
        >
          <i class="fa-regular fa-sun"></i>
        </button>
        <button
          v-if="isDark == false"
          type="button"
          @click="isDark = !isDark"
          class="block py-2 pl-3 pr-4 text-neutral-700 rounded hover:bg-neutral-100 md:hover:bg-transparent md:hover:text-cyan-700 md:p-0 :text-neutral-400 md::hover:text-cyan-500 :hover:bg-cyan-700 :hover:text-emerald-500 md::hover:bg-transparent :border-neutral-700"
        >
          <i class="fa-regular fa-moon"></i>
        </button>
      </div>
    </div>
    <a class="xl:hidden flex mr-6 items-center" href="#">
      <button
        v-if="isDark == true"
        type="button"
        class="block py-2 pl-3 pr-4 text-yellow-400 rounded md:hover:bg-transparent md:hover:text-cyan-700 md:p-0 :text-neutral-400 md::hover:text-cyan-500 :hover:bg-cyan-700 :hover:text-emerald-500 md::hover:bg-transparent :border-neutral-700"
        @click="isDark = !isDark"
      >
        <i class="fa-regular fa-sun"></i>
      </button>
      <button
        v-if="isDark == false"
        type="button"
        class="block py-2 pl-3 pr-4 text-cyan-700 rounded md:hover:bg-transparent md:hover:text-cyan-700 md:p-0 :text-neutral-400 md::hover:text-cyan-500 :hover:bg-neutral-700 :hover:text-gray-500 md::hover:bg-transparent :border-cyan-700"
        @click="isDark = !isDark"
      >
        <i class="fa-regular fa-moon"></i>
      </button>
    </a>
  </nav>
</template>

<style scoped>
i {
  font-size: 16pt;
}
</style>
