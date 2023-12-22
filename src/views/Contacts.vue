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

  <div class="container">
    <h1>Contact</h1>
    <form
      target="_blank"
      action="https://formsubmit.co/ilaria.galliano7@gmail.com"
      method="POST"
    >
      <div class="form-group">
        <div class="form-row">
          <div class="col-4">
            <input
              type="text"
              name="name"
              class="form-control"
              placeholder="Full Name"
              required
            />
          </div>
          <div class="col-4">
            <input
              type="email"
              name="email"
              class="form-control"
              placeholder="Email Address"
              required
            />
          </div>
        </div>
      </div>
      <div class="form-group">
        <textarea
          placeholder="Your Message"
          class="form-control"
          name="message"
          rows="10"
          required
        ></textarea>
      </div>
      <button type="submit" class="btn btn-lg btn-dark btn-block">
        Submit Form
      </button>
    </form>
  </div>
</template>

<script>
export default {
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

.blue-box {
  height: 200px;
  background: #9eaee2;
}
/* 
.jumbotron {
  background: #f19998;
} */

h1 {
  /* font-family: "Lucida Console", Monaco, monospace; */
  font-weight: bold;
}

li {
  list-style: none;
  padding: 10px;
}

/*TEST/ */
.form-container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
}

input[type="text"],
input[type="email"],
input[type="tel"] {
  width: 100%;
  padding: 8px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #4caf50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #45a049;
}
</style>
