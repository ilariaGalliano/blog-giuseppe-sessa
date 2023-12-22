<template>
<!-- CREARE FORM CHE MANDA MAIL DIRETTAMENTE -->
  <div class="blue-box"></div>
  <div class="jumbotron mt-5">
    <h1>Contatti</h1>
    <div>
      <span>Info</span>
      <p>
        <font-awesome-icon class="pr-3" icon="fa-video" />
        <a href="mailto:giuseppesessa54@gmail.com">giuseppesessa54@gmail.com</a>
      </p>
    </div>
    <div>
      <p>
        <font-awesome-icon class="pr-3" icon="fa-phone" />
        <span>+39 3545447898</span>
      </p>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

.blue-box {
  height: 200px;
  background: #9eaee2;
}

.jumbotron {
  background: #f19998;
}

h1 {
  /* font-family: "Lucida Console", Monaco, monospace; */
  font-weight: bold;
}

li {
  list-style: none;
  padding: 10px;
}

</style>
