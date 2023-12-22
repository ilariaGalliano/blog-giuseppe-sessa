<template>
  <div class="container">
    <div class="about">
      <h1>BIO</h1>
      <div class="flags">
        <select name="lang" v-model="lang">
          <option value="en">🇬🇧</option>
          <option value="it">🇮🇹</option>
        </select>
      </div>
      <div class="container pb-5">
        <div class="row">
          <div class="col-sm-1 col-md-2 col-lg-5">
            <p>
              {{ translate("bio") }}
            </p>
          </div>
          <div class="col-lg-2"></div>
          <div class="col-sm-1 col-md-2 col-lg-4 pb-4">
            <img
              class="card-img-top"
              src="../assets/concorso.jpeg"
              alt="Card image cap"
            />
          </div>
        </div>
        <div class="row">
          <div class="col-sm-1 col-md-2 col-lg-4 pb-3">
            <img
              class="card-img-top"
              src="../assets/gs.jpg"
              alt="Card image cap"
            />
          </div>
          <div class="col-2"></div>
          <div class="col-sm-1 col-md-2 col-lg-5">
            <p style="margin-bottom: 60px">
              {{ translate("bioSecondPart") }}
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-sm-1 col-md-2 col-lg-5 pb-3">
            <p>
              {{ translate("bioThirdPart") }}
            </p>
          </div>
          <div class="col-2"></div>
          <div class="col-sm-1 col-md-2 col-lg-4 pb-4">
            <img
              class="card-img-top"
              src="../assets/gs2.jpg"
              alt="Card image cap"
            />
          </div>
        </div>
        <div class="row">
          <div class="col-sm-1 col-md-2 col-lg-4 pb-3">
            <img
              class="card-img-top"
              src="../assets/exeter.jpg"
              alt="Card image cap"
            />
          </div>
          <div class="col-2"></div>
          <div class="col-sm-1 col-md-2 col-lg-5">
            <p style="margin-bottom: 60px">
              {{ translate("bioLastPart") }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import en from "../en.js";
import it from "../it.js";

export default {
  name: "Bio",
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
h1 {
  padding-top: 50px;
  margin-bottom: 50px;
}
.about {
  width: 100%;
  height: 100%;
  position: relative;
  top: 70px;
  text-align: center;
}
.flags {
  position: absolute;
  top: 104px;
  right: 0;
}

@media only screen and (max-width: 480px) {
  h1 {
    padding-top: 0;
  }
  .flags {
    position: absolute;
    top: 2%;
    right: 0;
  }
}
</style>
