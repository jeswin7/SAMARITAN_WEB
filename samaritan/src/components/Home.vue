<template>
  <div id="app">
    <!-- Landing Page -->
    <div class="landing-page">
      <img :src="logo" class="logo" />{{ brand }}
      <div class="nav">
        <ul>
          <li>Home</li>
          <li>About Us</li>
        </ul>
      </div>
      <div class="description">
        <h1>SETTLE SMART</h1>
        <p>
          We help international students find accommodation in Canada! Our idea
          is to connect seekers like you with experts in the accommodation
          domain(Mentors) to help you find a suitable accommodation even before
          you land in Canada!
        </p>
      </div>
      <div class="search-bar">
        <input type="text" placeholder="Cities" />
        <button>Search</button>
      </div>
    </div>

    <!-- Contact Page -->
    <div class="contact-page">
      <Form />
    </div>
      <div class="metrics">
        <p>SAMARITAN | Metrics</p>
      </div>
      <div class="footer">
      <img :src="logo" class="logo" />{{ brand }}
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
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  display: flex;
}
.logo {
  width: 100px;
}
.brand {
  color: #319f9f;
  font-size: 40px;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.landing-page {
  text-align: left;
}
</style>
