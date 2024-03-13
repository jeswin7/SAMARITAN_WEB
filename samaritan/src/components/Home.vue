<template>
  <div id="app">
    <!-- Landing Page -->
    <div class="landing-page">
      <div class="logo-brand-container">
        <img :src="logo" class="logo" />
        <span class="brand">{{ brand }}</span>
      </div>
      <div class="nav">
        <ul>
          <li>Home</li>
          <li>About Us</li>
        </ul>
      </div>
      <div class="description">
        <h1>SETTLE SMART</h1>
        <p>{{description}}</p>
      </div>
      <div class="search-bar">
        <input type="text" placeholder="Cities" />
        <button>Search</button>
      </div>
    </div>

    <!-- Contact Page -->
    <div class="contact-page">
      <div class="form-container">
        <Form />
      </div>
    </div>
          <div class="metrics">
        <p>SAMARITAN | Metrics</p>
      </div>
      <div class="footer">
        <img :src="logo" class="logo" /> {{brand}}
        <div class="social-media">
          <a href="#">Facebook</a>
          <a href="#">Twitter</a>
          <a href="#">Instagram</a>
        </div>
        <p>&copy; 2024 SAMARITAN. All rights reserved.</p>
      </div>
  </div>
</template>

<script>
import Form from "./ContactForm.vue";

export default {
  name: "HelloWorld",
  props: {
    brand: String,
  },
  components: {
    Form: Form,
  },
  data() {
    return {
      logo: require("../assets/samaritanLogo.png"),
      description:"We help international students find accommodation in Canada! Our idea is to connect seekers like you with experts in the accommodation domain(Mentors) to help you find a suitable accommodation even before you land in Canada!"
    };
  },
};
</script>

<style scoped>
#app {
  height: 100vh;
}

.logo-brand-container {
  display: flex;
  align-items: center;
  margin: 20px;
}

.logo {
  width: 75px;
  margin-right: 10px;
}

.brand {
  color: #319f9f;
  font-size: 24px;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 20px;
}

li {
  display: inline-block;
  margin: 0 10px;
}

.nav {
  display: flex;
  justify-content: flex-end;
}

.description {
  margin: 20px;
}

.search-bar {
  margin: 20px;
}

.landing-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-image: url('../assets/homeBG.jpg');
  background-size: cover;
  background-position: center;
}

.contact-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-image: url('../assets/contactFormBG.jpg');
  background-size: cover;
  background-position: center;
}

.form-container {
  width: 50%;
}

.metrics {
  background-color: black;
  color: white;
  text-align: center;
  padding: 20px;
  width: 100%;
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-color: black;
  color: white;
  width: 100%;
}

.social-media a {
  margin-right: 10px;
}
</style>
