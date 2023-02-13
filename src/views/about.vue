<script>
import { useDark, useToggle } from "@vueuse/core";
import footercomp from "../components/FooterComp.vue";
import headercomp from "../components/HeaderComp.vue";
import gridcomp from "../components/GridComp.vue";
import aboutcomp from "../components/AboutComp.vue";
export default {
  components: { headercomp, footercomp, gridcomp, aboutcomp },
  setup() {
    const isDark = useDark();
    const toggle = useToggle(isDark);
    return {
      isDark,
      toggle,
    };
  },
  data() {
    return {};
  },
  methods: {
    colorBody() {
      if (this.isDark == true) {
        return "bg-neutral-900 transition delay-150 duration-300 ease-in-out";
      } else {
        return "bg-white transition delay-150 duration-300 ease-in-out";
      }
    },
  },
};
</script>

<template>
  <body :class="colorBody()">
    <headercomp />
    <aboutcomp />
    <gridcomp />
    <footercomp />
  </body>
</template>
