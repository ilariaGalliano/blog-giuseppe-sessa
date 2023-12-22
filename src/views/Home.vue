<template>
  <!-- AGGIUNGERE COVER NUOVO ALBUM -->
  <div alt="image" class="home-img"></div>
  <div class="container">
    <!-- HomePage -->
    <h1 class="title">Giuseppe Sessa</h1>
    <div class="flags">
      <select name="lang" v-model="lang">
        <option value="en">🇬🇧</option>
        <option value="it">🇮🇹</option>
      </select>
    </div>
    <!-- Jumbotron -->
    <div class="card mb-5">
      <img class="card-img-top" src="../assets/gs2.jpg" alt="Card image cap" />
      <div class="card-body">
        <h5 class="card-title">Parker</h5>
        <p class="card-text">
          {{ translate("album") }}
        </p>
        <p class="card-text">
          <small class="text-muted">Last updated 3 mins ago</small>
        </p>
      </div>
    </div>
    <div class="card mt-3">
      <!-- <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a wider card with supporting text below as a natural lead-in
          to additional content. This content is a little bit longer.
        </p>
        <p class="card-text">
          <small class="text-muted">Last updated 3 mins ago</small>
        </p>
      </div>
      <img
        class="card-img-bottom"
        src="../assets/gs2.jpg"
        alt="Card image cap"
      /> -->
      <iframe
        style="border-radius: 12px"
        src="https://open.spotify.com/embed/artist/7ji3gKfLdWNIrV5i3jVZIW?utm_source=generator"
        width="100%"
        height="352"
        frameBorder="0"
        allowfullscreen=""
        allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
        loading="lazy"
      ></iframe>
    </div>
  </div>
</template>

<script>
import en from "../en.js";
import it from "../it.js";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

.title {
  margin-bottom: 55px;
  margin-top: 40px;
  /* font-family: "Lucida Console", Monaco, monospace; */
}

.home-img {
  width: 100%;
  height: 420px;
  background-image: url("../assets/gs.jpg");
  background-size: cover;
  text-align: center;
  position: relative;
  margin-bottom: 30px;
  z-index: 0;
}
.cd-img {
  width: 100%;
}

.flags {
  position: absolute;
  top: 65%;
  right: 14%;
}

@media only screen and (max-width: 480px) {
  h1 {
    padding-top: 0;
  }
  .flags {
    position: absolute;
    top: 68%;
    right: 10px;
  }
}
</style>
