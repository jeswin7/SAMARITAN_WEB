<template>
  <div class="search-bar">
    <b-input-group>
      <input
        type="text"
        placeholder="Destination City"
        class="searchBox form-control"
        v-model="searchCity"
      />
      <b-input-group-append>
        <button class="btn btn-primary searchBtn" @click="search">
          <i class="fas fa-search"></i>
        </button>
      </b-input-group-append>
    </b-input-group>
  </div>
  <div v-if="!isEmpty(results)" class="metricsContainer">
    <!-- Close button -->
    <div class="closeButton" @click="clearResults">
      <i class="fas fa-times"></i>
    </div>
    
    <!-- Metrics content -->
    <div class="metricsContainer">
      <div v-for="(value, key) in results" :key="key" class="metricsGrid">
        <p>
          <span class="themeMetricText">{{ value }}+ </span><br />
          {{ pascalToNormal(key) }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchCity: "",
      citiesAPI: {
        toronto: {
          rentals: 50,
          mentors: 15,
          rentLowerLimit: 700,
        },
        waterloo: {
          rentals: 40,
          mentors: 27,
          rentLowerLimit: 500,
        },
      },
      results: {},
    };
  },
  methods: {
    search() {
      if (this.citiesAPI[this.searchCity.toLowerCase()] !== undefined) {
        this.results = this.citiesAPI[this.searchCity.toLowerCase()];
      } else {
        this.results = {};
      }
    },
    clearResults() {
      this.results = {};
    },
    pascalToNormal(text) {
      return text.replace(/([A-Z])/g, " $1").replace(/^./, function (match) {
        return match.toUpperCase();
      });
    },
    isEmpty(obj) {
      return Object.keys(obj).length === 0;
    },
  },
};
</script>

<style scoped>
.searchBox {
  width: 80%;
  padding: 10px;
  border-top-left-radius: 20px;
  border-bottom-left-radius: 20px;
  border: 0;
}

.searchBtn {
  padding: 10px;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  background-color: white;
  color: #319f9f;
  border: 0;
}

.themeMetricText {
  color: #319f9f;
  font-weight: bold;
}

.metricsContainer {
  display: flex;
  flex-wrap: wrap;
  font-size: 25px;
  background-color: black;
  opacity: 80%;
  justify-content: flex-start;
  margin-top: 20px;
  border-radius: 20px;
  position: relative; /* Needed for absolute positioning of close button */
  width: 80%
}

.metricsGrid {
  margin: 20px;
}

.closeButton {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  color: #ffffff;
}
</style>
