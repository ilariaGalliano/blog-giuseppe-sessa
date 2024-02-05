<template>
  <div class="container mt-5">
    <h1 class="mb-5">Contacts</h1>
    <div class="display-flex">
      <div class="mr text-left">
        <span>Info</span>
        <p class="mt-2">
          <font-awesome-icon class="pr-3" icon="fa-video" />
          <a href="mailto:giuseppesessa54@gmail.com"
            >giuseppesessa54@gmail.com</a
          >
        </p>
        <p class="mb-mobile">
          <font-awesome-icon class="pr-3" icon="fa-phone" />
          <span>+39 3545447898</span>
        </p>
      </div>
      <form
        target="_blank"
        action="https://formsubmit.co/giuseppesessa54@gmail.com"
        method="POST"
      >
        <div class="form-group">
          <div class="form-row">
            <div class="col-4">
              <input
                type="text"
                name="name"
                class="form-control"
                placeholder="Your Name"
                required
              />
            </div>
            <div class="col-4">
              <input
                type="email"
                name="email"
                class="form-control"
                placeholder="Your Email"
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
            rows="5"
            required
          ></textarea>
        </div>
        <button type="submit" class="btn btn-lg btn-dark btn-block">
          Mail
        </button>
      </form>
    </div>
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

.mb-mobile {
  margin-bottom: 26px;
}

/* Medium Devices, Desktops */
@media only screen and (min-width: 992px) {
  .display-flex {
    display: flex;
    justify-content: center;
  }

  .mr {
    margin-right: 50px;
  }
}

/* Large Devices, Wide Screens */
@media only screen and (min-width: 1200px) {
  .display-flex {
    display: flex;
    justify-content: center;
  }

  .mr {
    margin-right: 50px;
  }
}

h1 {
  font-weight: bold;
}

li {
  list-style: none;
  padding: 10px;
}

.container {
  width: 100%;
  height: 100%;
  padding: 8% 5% 0 4%;
}

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
