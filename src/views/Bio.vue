<template>
  <div class="panel">
    <div class="container">
      <select name="lang" v-model="lang">
        <option value="en">🇬🇧</option>
        <option value="it">🇮🇹</option>
      </select>
      <!-- <p class="music_video fade-in intro">Giuseppe</p> -->
      <h2 class="music_video fade-in title-big">
        {{ translate("my") }} <br />
        {{ translate("story") }}
      </h2>
      <img
        src="../assets/exeter.jpg"
        alt="concert-pic"
        class="img-concert-pic"
      />
    </div>
  </div>

  <div class="panel">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        {{ translate("bio") }} <br />
      </h2>
      <!-- <p class="music_video fade-in subtitle">
        {{ translate("bioSecondPart") }}
      </p> -->
      <img
        src="../assets/2389landi-gio.jpg"
        alt="concert-pic"
        class="img-concert-pic"
      />
    </div>
  </div>

  <div class="panel">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        {{ translate("bioSecondPart") }} <br />
      </h2>
      <!-- <p class="music_video fade-in subtitle">
        {{ translate("bioLastPart") }}
      </p> -->
      <img
        src="../assets/2390landi-gio.jpg"
        alt="concert-pic"
        class="img-concert-pic"
      />
    </div>
  </div>

  <div class="panel">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        {{ translate("bioThirdPart") }} <br />
      </h2>
      <!-- <p class="music_video fade-in subtitle">
        {{ translate("bioLastPart") }}
      </p> -->
      <img
        src="../assets/7-2386landi-gio.jpg"
        alt="concert-pic"
        class="img-concert-pic"
      />
    </div>
  </div>

  <div class="panel">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        {{ translate("bioLastPart") }} <br />
      </h2>
      <!-- <p class="music_video fade-in subtitle">
        {{ translate("bioLastPart") }}
      </p> -->
      <img
        src="../assets/2326landi-gio.jpg"
        alt="concert-pic"
        class="img-concert-pic"
      />
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
}
li {
  list-style: none;
}

/* General style */

body {
  font-family: "Intro", sans-serif;
  font-size: 16px;
  box-sizing: border-box;
  background: #000;
}

/* Video  */
/* .video-bg {
  width: 100%;
  max-height: 600px;
  position: fixed;
  top: 0;
  left: 0;
  object-fit: cover;
  opacity: 0, 6;
  z-index: 0;
} */

/* Sections styles  */
.section {
  /*border: 1px solid red;*/
  position: relative;
  z-index: 1;
  width: 100%;
}

.title {
  text-align: center;
  /* width: 100%; */
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  max-width: 50%;
  position: fixed;
  top: 0;
  left: 0;
  margin-left: 25%;
  transform: scale(1);
  transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
  opacity: 0;
}

.section.in-page .title {
  transform: scale(1.2);
  opacity: 1;
}

.panel {
  /* height: 100vh; */
  width: 100%;
  background-color: #f7f7f7;
  color: #000;
  position: relative;
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  /* border: 1px solid red; */
  width: 100%;
  max-width: 900px;
  height: 100%;
  padding: 8% 5% 0 4%;
}

.intro {
  font-size: 20px;
  font-weight: bold;
}

.title-big {
  font-size: 4rem;
}

.fade-in {
  opacity: 0;
  transform: translateY(20vh);
  transition: all 1s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.fade-in.in-page {
  opacity: 1;
  transform: translateY(0vh);
}

.img-concert-pic {
  width: 100%;
  display: block;
  position: relative;
  margin-top: 30px;
}

.title-med {
  font-size: 1.3rem;
}

.subtitle {
  font-size: 1rem;
  color: #666;
  max-width: 500px;
  padding-bottom: 10px;
}

.orange-text {
  font-size: 2rem;
  color: #f56900;
  text-align: center;
  font-weight: bold;
}
</style>

<script>
import en from "../en.js";
import it from "../it.js";

export default {
  name: "Bio",
  mixins: [en, it],
  props: {
    msg: String,
  },
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
  mounted: function () {
    var element_to_watch = document.querySelectorAll(".music_video");

    // Callback
    var callback = function (items) {
      items.forEach((item) => {
        if (item.isIntersecting) {
          item.target.classList.add("in-page");
        } else {
          item.target.classList.remove("in-page");
        }
      });
    };

    // Observer:
    // Nuova caratteristica JS -- esegue una funzione di callback
    // che controlla elementi passati; se stanno entrando nella pagina li aggiunge se no
    //va a rimuovere la classe
    var observer = new IntersectionObserver(callback, { threshold: 0.6 });
    // threshold 0.5 --> quando arrivo al 60 % della sezione

    //apply
    element_to_watch.forEach((element) => {
      observer.observe(element);
      console.log(observer.observe(element));
    });
  },
};
</script>
