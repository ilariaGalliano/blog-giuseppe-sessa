<template>
  <div class="panel">
    <div class="container">
      <p class="music_video fade-in intro">Concert Dates</p>
      <h2 class="music_video fade-in title-big">
        Le nuove <br />
        date.
      </h2>
      <img src="../assets/live.jpg" alt="concert-pic" class="img-concert-pic" />
    </div>
  </div>

  <div class="panel mb-3">
    <div class="container">
      <h2 class="music_video fade-in title-med">
        Gli eventi <br />
        disponibili
      </h2>
      <p class="music_video fade-in subtitle">Napoli - 12 Maggio 2024 </p>
      <p class="music_video fade-in subtitle">Roma - 2 Giugno 2024</p>
      <p class="music_video fade-in subtitle">Milano - 20 Luglio 2024</p>
    </div>
  </div>
 
  <div class="row d-flex justify-content-center">
    <div>
      <h2 class="mt-4">Buy your tickets:</h2>
      <!-- Modal -->
      <button type="button" class="btn btn-info mt-3" @click="openModal">
        Info
      </button>
      <div v-if="isModalOpen" class="card-info">
        <p class="mb-2">Follow the instructure:</p>
        <ul>
          <li>
            Send a mail to:
            <a href="mailto:giuseppesessa54@gmail.com"
              >giuseppesessa54@gmail.com</a
            >
            or go to the <a href="/contacts">Contact page</a>
          </li>
          <li>You'll be contact back in 24 hours</li>
          <li>Buy your ticket</li>
          <li>Enjoy the concert</li>
        </ul>
        <button type="button" class="btn btn-info mt-3" @click="openModal">
          Close
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
}
</style>

<script>
export default {
  name: "Live",
  props: {
    msg: String,
    visible: Boolean,
  },
  data() {
    return {
      isModalOpen: this.visible,
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = !this.isModalOpen;
      console.log("test", this.isModalOpen);
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
