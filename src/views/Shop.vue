<template>
  <div alt="image" class="home-img"></div>
  <div class="container">
    <div class="flags">
      <select name="lang" v-model="lang">
        <option value="en">🇬🇧</option>
        <option value="it">🇮🇹</option>
      </select>
    </div>
    <!-- HomePage -->
    <h1 class="title">{{ translate("store") }}</h1>
    <!-- Jumbotron -->
    <div class="row d-flex justify-content-center" style="margin-bottom: 60px">
      <div class="mobile-mb">
        <div class="card" style="width: 18rem">
          <img
            class="card-img-top"
            style="width: 285px; height: 150px"
            src="../assets/comingsoon.jpeg"
            alt="Card image cap"
          />
          <div class="card-body">
            <h5 class="card-title">Parker (coming soon)</h5>
            <p class="card-text">{{ translate("album") }}</p>
            <a href="#" class="btn btn-info disabled">Buy</a>
          </div>
        </div>
      </div>
      <div class="mobile-mb">
        <div class="card" style="width: 18rem">
          <img
            class="card-img-top"
            src="../assets/gs2.jpg"
            alt="Card image cap"
          />
          <div class="card-body">
            <h5 class="card-title">Orizzonte</h5>
            <p class="card-text">{{ translate("oldAlbum") }}</p>
            <a
              href="https://orizzonteshop.company.site/"
              class="btn btn-info"
              target="_blank"
              >Buy</a
            >
          </div>
        </div>
      </div>
    </div>

    <div>
      <div
        class="row d-flex justify-content-center"
        style="margin-bottom: 60px"
      >
        <div class="mobile-mb">
          <div class="card" style="width: 18rem">
            <img
              class="card-img-spartito"
              src="../assets/spartito1.png"
              alt="Card image cap"
            />
            <div class="card-body">
              <h5 class="card-text">How I Met Your Mother</h5>
              <p class="card-text">{{ translate("spartito") }}</p>
              <download-pdf-button
                :pdf-url="pdfUrl"
                :pdf-file-name="pdfFileName"
              />
            </div>
          </div>
        </div>
        <div class="mobile-mb">
          <div class="card" style="width: 18rem">
            <img
              class="card-img-spartito"
              src="../assets/spartito2.png"
              alt="Card image cap"
            />
            <div class="card-body">
              <h5 class="card-text">Stand by Me</h5>
              <p class="card-text">{{ translate("spartito") }}</p>
              <download-pdf-button
                :pdf-url="pdfUrl2"
                :pdf-file-name="pdfFileName2"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div
        class="row d-flex justify-content-center"
        style="margin-bottom: 60px"
      >
        <div class="mobile-mb">
          <div class="card" style="width: 18rem">
            <img
              class="card-img-spartito"
              style="padding: 10px"
              src="../assets/spartito3.png"
              alt="Card image cap"
            />
            <div class="card-body">
              <h5 class="card-text">Anne & Rose</h5>
              <p class="card-text">{{ translate("spartito") }}</p>
              <a
                href="https://orizzonteshop.company.site/ANNE-&-ROSE-TAB-p625095818"
                class="btn btn-info"
                target="_blank"
                >Buy</a
              >
            </div>
          </div>
        </div>
        <div class="mobile-mb">
          <div class="card" style="width: 18rem">
            <img
              class="card-img-spartito"
              style="padding: 10px"
              src="../assets/spartito4.png"
              alt="Card image cap"
            />
            <div class="card-body">
              <h5 class="card-text">Parker</h5>
              <p class="card-text">{{ translate("spartito") }}</p>
              <a
                href="https://orizzonteshop.company.site/PARKER-TAB-p625092054"
                class="btn btn-info"
                target="_blank"
                >Buy</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="row d-flex justify-content-center">
      <div>
        <h2 class="mt-4">{{ translate("booking") }}</h2>
        <!-- Modal -->
        <button type="button" class="btn btn-info mt-3" @click="openModal">
          Info
        </button>
        <div v-if="isModalOpen" class="card-info">
          <p>{{ translate("instruction") }}</p>
          <ul class="mb-2">
            <li>
              {{ translate("mail") }}
              <a href="mailto:giuseppesessa54@gmail.com"
                >giuseppesessa54@gmail.com</a
              >
              {{ translate("visit") }} <a href="/contacts">Contact page</a>
            </li>
            <li>{{ translate("contact") }}</li>
            <li>{{ translate("reserve") }}</li>
            <li>{{ translate("enjoy") }}</li>
          </ul>
          <button type="button" class="btn btn-info mt-3" @click="openModal">
            {{ translate("close") }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import DownloadPdfButton from "@/components/DownloadPdfButton.vue";
import en from "../en.js";
import it from "../it.js";
export default {
  name: "Shop",
  components: {
    DownloadPdfButton,
  },
  props: {
    visible: Boolean,
    msg: String,
  },
  mixins: [en, it],
  data() {
    return {
      isModalOpen: this.visible,
      pdfUrl: "/files/HIMYM.pdf",
      pdfFileName: "HIMYM.pdf",
      pdfUrl2: "/files/StandByMe.pdf",
      pdfFileName2: "StandByMe.pdf",
      pdfUrl3: "/files/Anne&Rose.pdf",
      pdfFileName3: "Anne&Rose.pdf",
      pdfUrl4: "/files/PARKER.pdf",
      pdfFileName4: "PARKER.pdf",
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
.flags {
  position: absolute;
  right: 29%;
  top: 60%;
}

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
  .flags {
    position: absolute;
    top: 78%;
    right: 10px;
  }
}
</style>
