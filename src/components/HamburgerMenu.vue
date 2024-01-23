<template>
  <div>
    <button class="hamburger-menu" @click="toggleMenu">
      <span class="hamburger-menu__line"></span>
      <span class="hamburger-menu__line"></span>
      <span class="hamburger-menu__line"></span>
    </button>
    <ul v-if="isOpen" class="menu-items">
      <li><router-link to="/" @click="toggleMenu">Home</router-link></li>
      <li><router-link to="/bio" @click="toggleMenu">About</router-link></li>
      <li><router-link to="/shop" @click="toggleMenu">Shop</router-link></li>
      <li>
        <router-link to="/live" @click="toggleMenu">Concert Dates</router-link>
      </li>
      <li>
        <router-link to="/contacts" @click="toggleMenu">Contacts</router-link>
      </li>
      <!-- <li>
        <select name="lang" v-model="lang">
          <option value="en">🇬🇧&emsp;English</option>
          <option value="it">🇮🇹&emsp;Italiano</option>
        </select>
      </li> -->
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return { isOpen: false };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style>
.hamburger-menu {
  display: none;
}

@media (max-width: 700px) {
  .hamburger-menu {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border: none;
    cursor: pointer;
  }
  .hamburger-menu__line {
    display: block;
    width: 30px;
    height: 3px;
    margin: 5px;
    background-color: #000;
    border-radius: 3px;
  }
  .menu-items {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 0;
    margin: 0;
    list-style: none;
  }
  .menu-items li {
    margin: 10px;
  }
  .menu-items li a {
    text-decoration: none;
    color: #000;
  }
}
</style>
