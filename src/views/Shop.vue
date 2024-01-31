<!-- eslint-disable prettier/prettier -->
<template>
 <div alt="image" class="home-img"></div>
  <div class="container">
      <!-- HomePage -->
      <h1 class="title">Official Store</h1>
      <!-- Jumbotron -->
        <div class="row d-flex justify-content-center" style="margin-bottom: 60px">
          <div class="mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/gs2.jpg" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-title">Parker</h5>
                <p class="card-text">Listen my new Album</p>
                <a href="#" class="btn btn-info">Buy</a>
              </div>
            </div>
          </div>
          <div class="mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/gs2.jpg" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-title">Orizzonte</h5>
                <p class="card-text">Listen to my music</p>
                <a href="https://orizzonteshop.company.site/" class="btn btn-info" target="_blank">Buy</a>
              </div>
            </div>
          </div>
        </div>
   
      <div>
        <div class="row d-flex justify-content-center" style="margin-bottom: 60px">
          <div class="mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-spartito" src="../assets/spartito1.png" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-text">Stand by Me</h5>
                <p class="card-text">Download the sheet music</p>
                <download-pdf-button :pdf-url="pdfUrl" :pdf-file-name="pdfFileName" /> 
              </div>
            </div>
          </div>
          <div class="mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-spartito" src="../assets/spartito2.png" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-text">How I Met Your Mother</h5>
                <p class="card-text">Download the sheet music</p>
                <download-pdf-button :pdf-url="pdfUrl2" :pdf-file-name="pdfFileName2" /> 
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row d-flex justify-content-center">
      <div>
        <h2 class="mt-4">Book your class:</h2>
        <!-- Modal -->
       <button type="button" class="btn btn-info mt-3" @click="openModal">Info</button>
       <div v-if="isModalOpen" class="card-info">
        <p>Follow the instructure:</p>
        <ul class="mb-2">
            <li>Send a mail to: <a href="mailto:giuseppesessa54@gmail.com">giuseppesessa54@gmail.com</a> or go to the <a href="/contacts">Contact page</a> </li>
            <li>You'll be contact back in 24 hours</li>
            <li>Reserve your music class</li>
            <li>Enjoy it</li>
        </ul>
        <button type="button" class="btn btn-info mt-3" @click="openModal">Close</button>
       </div>
      </div>
    </div>
    </div>
</template>

<script>
import DownloadPdfButton from "@/components/DownloadPdfButton.vue";
export default {
  name: "Shop",
  components: {
    DownloadPdfButton,
  },
  props: {
    visible: Boolean,
  },
  data() {
    return {
      isModalOpen: this.visible,
      pdfUrl: "/files/HIMYM.pdf",
      pdfFileName: "HIMYM.pdf",
      pdfUrl2: "/files/StandByMe.pdf",
      pdfFileName2: "StandByMe.pdf",
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = !this.isModalOpen;
      console.log("test", this.isModalOpen);
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

.title-footer {
  padding-top: 75px;
}

.home-img {
  width: 100%;
  height: 420px;
  background-image: url("../assets/cd.jpg");
  background-size: cover;
  text-align: center;
  position: relative;
  margin-bottom: 30px;
  z-index: 0;
}
.cd-img {
  width: 100%;
}

.card-img-spartito {
  filter: blur(6px);
  height: 150px;
}

.card-img-spartito:hover {
  filter: blur(0);
}
.card:hover {
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.3);
  transition: all 150ms ease-in-out;
  transform: scale(1);
  opacity: 1;
  cursor: pointer;
  border-radius: 0.25%;
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

.mobile-mb {
  margin: 15px;
}

li {
  text-align: initial;
}

/* .googleCalendar {
  position: relative;
  height: 0;
  width: 50%;
  padding-bottom: 50%;
}

.googleCalendar iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
} */
@media only screen and (max-width: 480px) {
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
  .card:hover {
    box-shadow: 0 0 50px rgba(0, 0, 0, 0.3);
    transition: all 150ms ease-in-out;
    transform: scale(1);
    opacity: 1;
    cursor: pointer;
  }
  .card-img-spartito {
    filter: blur(6px);
  }

  .card-img-spartito:hover {
    filter: blur(0);
  }
}
</style>
