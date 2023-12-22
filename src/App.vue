<template id="app">
  <NavBarView />
  <router-view />
  <FooterView />
</template>

<script>
import FooterView from "./components/FooterView.vue";
import NavBarView from "./components/NavBarView.vue";
import en from "./en.js";
import it from "./it.js";

export default {
  name: "App",
  components: {
    FooterView,
    NavBarView,
  },
  mixins: [en, it],
  data() {
    return {
      lang: "en",
    };
  },
  methods: {
    translate(prop) {
      return this[this.lang][prop];
    },
  },
};
</script>

<style>
#app {
  font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
}
</style>
