<script>
import { useDark, useToggle } from "@vueuse/core";
import headingcomp from "../components/HeadingComp.vue";
import headercomp from "../components/HeaderComp.vue";
import footercomp from "../components/FooterComp.vue";
export default {
  components: { headercomp, footercomp, headingcomp },
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
    <div class="m-20"></div>
    <headingcomp />
    <footercomp />
  </body>
</template>
