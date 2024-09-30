<template>
  <div class="panel">
    <div class="container">
      <div class="flags mt-3">
        <select name="lang" v-model="lang">
          <option value="en">🇬🇧</option>
          <option value="it">🇮🇹</option>
        </select>
      </div>
      <h2 class="music_video fade-in title-big">
        {{ translate("concert") }} <br />
        {{ translate("dates") }}
      </h2>
      <img src="../assets/live.jpg" alt="concert-pic" class="img-concert-pic" />
    </div>
  </div>

  <div class="panel mb-3">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        {{ translate("upcoming") }}<br />
        {{ translate("events") }}
      </h2>
      <p class="music_video fade-in subtitle">
        Terni - Auditorium Gazzoli - 23 Febbraio - Opening Mike Dawes -
        <a
          href="https://www.vivaticket.com/it/ticket/mike-dawes-the-italian-tour/225180?culture=it-it"
          target="_blank"
          style="color: #aa8a85; font-weight: bold"
          >{{ translate("buyHere") }}</a
        >
      </p>
      <p class="music_video fade-in subtitle">
        Roma - Let It Beer - 25 Febbraio - Opening Mike Dawes -
        <a
          href="ttps://www.ciaotickets.com/it/biglietti/mike-dawes-live-in-roma"
          target="_blank"
          style="color: #aa8a85; font-weight: bold"
          >{{ translate("buyHere") }}</a
        >
      </p>
    </div>
  </div>

  <div class="row d-flex justify-content-center">
    <div>
      <h2 class="mt-4">{{ translate("buy") }}</h2>
      <!-- Modal -->
      <button type="button" class="btn btn-success" @click="openModal">
        Info
      </button>
      <div v-if="isModalOpen" class="card-info">
        <p>{{ translate("instruction") }}</p>
        <ul class="mb-2">
          <li>
            {{ translate("mail") }}
            <a href="mailto:giuseppesessa54@gmail.com"
              >giuseppesessa54@gmail.com</a>
          </li>
          <li>{{ translate("contact") }}</li>
          <li>{{ translate("buyInfo") }}</li>
          <li>{{ translate("enjoy") }}</li>
        </ul>
        <button type="button" class="btn btn-success mt-3" @click="openModal">
          {{ translate("close") }}
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
}
li {
  text-align: initial;
}

/*/
/* General style */

body {
  font-size: 16px;
  box-sizing: border-box;
  background: #000;
}

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
  height: auto;
  width: 100%;
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
  padding: 7% 5% 0 4%;
}

.intro {
  font-size: 20px;
  font-weight: bold;
}

.title-big {
  font-size: 5rem;
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
}

.title-med {
  font-size: 3.5rem;
}

.subtitle {
  font-size: 1.5rem;
  color: #666;
  /* max-width: 500px; */
  padding-bottom: 10px;
}

.orange-text {
  font-size: 2rem;
  color: #f56900;
  text-align: center;
  font-weight: bold;
}

.card-info {
  width: 300px;
  height: auto;
  border: 2px solid grey;
  border-radius: 40px;
  padding: 10px;
  margin-top: 20px;
  margin-left: 7px;
}

h2 {
  margin-bottom: 30px;
}

@media only screen and (max-width: 480px) {
  .container {
    margin-bottom: 20px;
    margin-top: 20px;
  }

  h2 {
    margin-bottom: 30px;
  }
  .mobile-mb {
    margin-bottom: 15px;
  }
  .card-info {
    width: 300px;
    height: auto;
    border: 2px solid grey;
    border-radius: 40px;
    padding: 10px;
    margin-top: 20px;
    margin-left: 7px;
  }
  .title-big {
    font-size: 3rem;
    margin-top: 6px;
  }
  .title-med {
    font-size: 1.5rem;
  }
  .subtitle {
    font-size: 1rem;
  }
}
</style>

<script>
import en from "../en.js";
import it from "../it.js";
export default {
  name: "Live",
  props: {
    msg: String,
    visible: Boolean,
  },
  mixins: [en, it],
  data() {
    return {
      isModalOpen: this.visible,
      lang: "en",
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = !this.isModalOpen;
      console.log("test", this.isModalOpen);
    },
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
