<!-- Footer -->
<template>
  <footer>
    <h3 class="title-footer">Giuseppe Sessa</h3>
    <div>
      <ul class="d-flex justify-content-center" style="padding-left: 0">
        <li>
          <a href="https://www.youtube.com/@giuseppesessa8166" target="_blank">
            <img src="../assets/ytube.png" alt="fb" width="44" height="30" />
          </a>
        </li>
        <li>
          <a
            href="https://it-it.facebook.com/GiuseppeSessaMusic/"
            target="_blank"
          >
            <img
              src="../assets/instagram.png"
              alt="instagram"
              width="30"
              height="30"
            />
          </a>
        </li>
        <li>
          <a
            href="https://open.spotify.com/artist/7ji3gKfLdWNIrV5i3jVZIW"
            target="_blank"
          >
            <img src="../assets/spotify.png" alt="yt" width="30" height="30" />
          </a>
        </li>
      </ul>
      <p>© {{ currYear }} Giuseppe Sessa</p>
    </div>
  </footer>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

.title-footer {
  padding-top: 75px;
  margin-left: 24px;
}

li {
  list-style: none;
  padding: 10px;
}

img {
  transition: transform 0.2s;
}

img:hover {
  transform: scale(1.3);
}

footer {
  height: 300px;
  background-color: #aa8a85;
  color: #fff;
  margin-top: 50px;
  z-index: 2;
}
</style>

<script>
export default {
  data() {
    return {
      currYear: new Date().getFullYear(),
    };
  },
};
</script>
