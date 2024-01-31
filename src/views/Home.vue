<template>
  <!-- AGGIUNGERE COVER NUOVO ALBUM -->
  <div alt="image" class="home-img"></div>
  <div class="container">
    <!-- HomePage -->
    <!-- <h1 class="title">Giuseppe Sessa</h1> -->
    <img class="title-name" src="../assets/logo-nome.png" alt="npme" />
    <div class="flags">
      <select name="lang" v-model="lang">
        <option value="en">🇬🇧</option>
        <option value="it">🇮🇹</option>
      </select>
    </div>
    <!-- Jumbotron -->
    <div class="card" style="margin-bottom: 60px">
      <iframe
        height="400"
        src="https://www.youtube.com/embed/P7K453_wXSk?autoplay=1&mute=1&loop=1"
        title="Giuseppe Sessa video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      ></iframe>
    </div>

    <div class="card mb-5">
      <img
        class="card-img-top"
        src="../assets/NewAlbum.jpeg"
        alt="Card image cap"
      />
      <div class="card-body">
        <h5 class="card-title">Parker</h5>
        <p class="card-text">
          {{ translate("album") }}
        </p>
      </div>
    </div>
    <div class="card mb-5">
      <img
        class="card-img-top"
        src="../assets/song.jpeg"
        alt="Card image cap"
      />
      <div class="card-body">
        <h5 class="card-title">Parker</h5>
        <p class="card-text">
          {{ translate("album") }}
        </p>
      </div>
    </div>
    <div class="card mb-5">
      <img class="card-img-top" src="../assets/gs2.jpg" alt="Card image cap" />
      <div class="card-body">
        <h5 class="card-title">Parker</h5>
        <p class="card-text">
          {{ translate("album") }}
        </p>
      </div>
    </div>
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
}

.home-img {
  width: 100%;
  height: 530px;
  background-image: url("../assets/homepage.jpg");
  background-size: cover;
  background-position: center;
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
  top: 80%;
  right: 14%;
}

@media only screen and (max-width: 480px) {
  h1 {
    padding-top: 0;
  }
  .flags {
    position: absolute;
    top: 73%;
    right: 10px;
  }

  .title-name {
    width: 100%;
  }

  .home-img {
    height: 420px;
  }
}
</style>
