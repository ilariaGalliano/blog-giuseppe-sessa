<!-- eslint-disable prettier/prettier -->
<template>
 <div alt="image" class="home-img"></div>
  <div class="container">
      <!-- HomePage -->
      <h1 class="title">Official Store</h1>
      <!-- Jumbotron -->
        <div class="row d-flex justify-content-center" style="margin-bottom: 60px">
          <div class="col-sm-1 	col-md-4 	col-lg-4 mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/gs2.jpg" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-title">New Cd</h5>
                <p class="card-text">Listen my new Album</p>
                <a href="#" class="btn btn-info">Buy</a>
              </div>
            </div>
          </div>
          <div class="col-sm-1 	col-md-4 	col-lg-4 mobile-mb">
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
          <div class="col-sm-1 	col-md-4 	col-lg-4 mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/live2.jpg" alt="Card image cap">
              <div class="card-body">
                <h5 class="card-title">Spartito</h5>
                <p class="card-text">Download my Spartito</p>
                <download-pdf-button :pdf-url="pdfUrl" :pdf-file-name="pdfFileName" /> 
              </div>
            </div>
          </div>
          <div class="col-sm-1 	col-md-4 	col-lg-4 mobile-mb">
            <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/live2.jpg" alt="Card image cap">
              <div class="card-body">
                 <h5 class="card-title">Spartito</h5>
                <p class="card-text">Download my Spartito</p>
                <download-pdf-button :pdf-url="pdfUrl" :pdf-file-name="pdfFileName" /> 
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row d-flex justify-content-center">
      <div class="col-sm-1 	col-md-4 	col-lg-4">
        <h2 class="mt-4">Book your class:</h2>
        <!-- Modal -->
       <button type="button" class="btn btn-info mt-3" @click="openModal">Info</button>
       <div v-if="isModalOpen" class="card-info">
        <p>Follow the instructure:</p>
        <ul>
            <li>Send a mail to: <a href="mailto:giuseppesessa54@gmail.com">giuseppesessa54@gmail.com</a> </li>
            <li>You'll be contact back in 24 hours</li>
            <li>Reserve your music class</li>
            <li>Enjoy it</li>
        </ul>
        <button type="button" class="btn btn-info mt-3" @click="openModal">Close</button>
       </div>
      </div>
    </div>
        <!-- <div class="mt-4 googleCalendar">
            <iframe src="https://calendar.google.com/calendar/embed?height=600&wkst=1&bgcolor=%23ffffff&ctz=Europe%2FRome&showTitle=1&showNav=1&showDate=1&showTz=1&src=aWxhcmlhLmdhbGxpYW5vN0BnbWFpbC5jb20&src=YWRkcmVzc2Jvb2sjY29udGFjdHNAZ3JvdXAudi5jYWxlbmRhci5nb29nbGUuY29t&src=aXQuaXRhbGlhbiNob2xpZGF5QGdyb3VwLnYuY2FsZW5kYXIuZ29vZ2xlLmNvbQ&src=NWh0MXY0N2lzMXVoYTBoaTdtanN1M29tZzY0djFpcWhAaW1wb3J0LmNhbGVuZGFyLmdvb2dsZS5jb20&color=%237986CB&color=%2333B679&color=%230B8043&color=%234285F4" style="border:solid 1px #777" width="800" height="600" frameborder="0" scrolling="no"></iframe>
        </div> -->
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
      pdfUrl: "/files/ricevuta_terzoAcconto.pdf",
      pdfFileName: "ricevuta_terzoAcconto.pdf",
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

.card-body:hover {
  box-shadow: 0 0 50px rgba(0, 0, 0, 0.3);
  transition: all 150ms ease-in-out;
  transform: scale(1);
  opacity: 1;
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
    margin-top: 20px;
  }
}
</style>
