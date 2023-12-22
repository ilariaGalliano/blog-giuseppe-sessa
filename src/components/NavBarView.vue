<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/bio">Bio</router-link> |
    <router-link to="/shop">Shop</router-link> |
    <router-link to="/live">Live</router-link> |
    <router-link to="/contacts">{{ translate("contacts") }}</router-link>
    <!-- |
    <select name="lang" v-model="lang">
      <option value="en">🇬🇧</option>
      <option value="it">🇮🇹</option>
    </select> -->
    <!-- <h3>{{ translate("welcomeMsg") }}</h3>
    <h3>{{ translate("mainPage") }}</h3> -->
  </div>
  <HamburgerMenu />
  <!-- <button @click="translate('welcomeMsg')">click</button> -->
</template>

<script>
import en from "../en.js";
import it from "../it.js";
import HamburgerMenu from "./HamburgerMenu.vue";

export default {
  name: "App",
  components: {
    HamburgerMenu,
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
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 50px;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 87px;
  z-index: 18;
  background: rgba(31, 31, 31, 0.47);
  /* background: #f0d480; */
  display: block;
  transform: translate3d(0px, 0px, 0px);
  margin-bottom: 30px;
}

#nav a {
  font-weight: bold;
  /* color: #2c3e50; */
  color: #fff;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

#mobile-nav {
  padding: 50px;
  position: fixed;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 87px;
  z-index: 18;
  background: rgba(31, 31, 31, 0.47);
  /* background: #f0d480; */
  display: block;
  transform: translate3d(0px, 0px, 0px);
  margin-bottom: 30px;
}

.dropdown-nav {
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100%;
  max-width: 250px;
  height: 100%;
  background: #fff;
  top: 0;
  left: 0;
}

.dropdown-nav li {
  margin-left: 0;
  text-decoration: none;
}

/* Custom, iPhone Retina */
@media only screen and (min-width: 320px) {
}

/* Extra Small Devices, Phones */
@media only screen and (min-width: 480px) {
}

/* Small Devices, Tablets */
@media only screen and (min-width: 768px) {
}

/* Medium Devices, Desktops */
@media only screen and (min-width: 992px) {
}

/* Large Devices, Wide Screens */
@media only screen and (min-width: 1200px) {
}
.link {
  font-size: 14px;
  transition: 0.5s ease all;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
}

.link:hover {
  color: #00afea;
  border-color: #00afea;
}

.icon {
  display: flex;
  align-items: center;
  position: absolute;
  top: 0;
  right: 24px;
  height: 100%;
}

font-awesome-icon {
  cursor: pointer;
  font-size: 24px;
  transition: 0.8s ease all;
}

.icon-active {
  transform: rotate(180deg);
}

@media (max-width: 700px) {
  #nav {
    display: none;
  }
}
/* @media (min-width: 1240px) {
  header {
    max-width: 1240px;
  }
  #nav {
    max-width: 1240px;
  }
} */
</style>
