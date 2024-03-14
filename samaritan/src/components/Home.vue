<template>
  <div id="app">
    <!-- Landing Page -->
    <div class="landing-page">
      <div class="logo-brand-container">
        <img :src="logo" class="logo" />
        <span class="brand">{{ brand }}</span>
        <div class="nav">
          <ul>
            <li class="active">Home</li>
            <li>About</li>
          </ul>
        </div>
      </div>

      <div class="description">
        <p>
          <span class="subHeading">SETTLE SMART</span><br />
          We help international students find accommodation in Canada!<br />
          Our idea is to connect seekers like you with experts in the
          accommodation domain (Mentors) to help you find a suitable
          accommodation even before you land in Canada!
        </p>
        <SearchBox />
      </div>
    </div>

    <!-- Contact Page -->
    <div class="contact-page">
      <div class="form-container">
        <Form />
      </div>
    </div>
    <div class="metrics">
      <MetricsView /> <!-- Renamed component -->
    </div>
    <div class="line"></div>

    <div class="footer">
      <div class="logo-brand-container">
        <img :src="logo" class="logo" />
        <span class="brand">{{ brand }}</span>
      </div>
      <p class="copyright">&copy; 2024 SAMARITAN | All rights reserved.</p>
      <div class="social-media">
        <div class="social-media">
          <i class="fab fa-facebook"></i>
          <i class="fab fa-youtube"></i>
          <i class="fab fa-twitter"></i>
          <i class="fab fa-instagram"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Form from "./ContactForm.vue";
import MetricsView from './MetricsView.vue';
import SearchBox from './SearchCities.vue';

export default {
  name: "HelloWorld",
  props: {
    brand: String,
  },
  components: {
    Form,
    MetricsView,
    SearchBox
  },
  data() {
    return {
      logo: require("../assets/samaritanLogo.png"),
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

.subHeading {
  color: #319f9f;
  font-weight: bold;
}

.nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.nav ul {
  display: inline-block;
  margin-left: 20px;
  color: white;
}

.nav {
  margin-right: 20px;
  justify-content: flex-end;
}

.active {
  font-weight: bold;
  border-bottom-color: #319f9f;
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

.description {
  margin-top: 10%;
  padding: 10px;
  color: white;
  width: 50rem;
  text-align: left;
  font-size: 25px;
}

.landing-page {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background-image: url("../assets/homeBG.png");
  background-size: cover;
  background-position: center;
  background-color: black;
}

.contact-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-image: url("../assets/contactFormBG.jpg");
  background-size: cover;
  background-position: center;
}

.form-container {
  width: 50%;
}

.metrics {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
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

.social-media {
  margin-right: 20px;
}

.social-media a {
  margin-right: 10px;
}

.line {
  height: 2px;
  width: 100%;
  background-color: white;
}

.footer .copyright {
  text-align: center;
  margin: 0;
  flex: 1;
}

.fab {
  padding: 10px;
}
</style>
