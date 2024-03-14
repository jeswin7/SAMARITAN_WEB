<template>
  <div class="metricsContainer">
    <div v-for="(value, key) in metricData" :key="key" class="metricsGrid">
      <p class="themeMetricText">{{ value }}</p>
      {{ pascalToNormal(key) }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      metricData: {
        mentors: "100+",
        happySeekers: "1500+",
        targetCities: "50+",
      },
    };
  },
  methods: {
    pascalToNormal(text) {
      return text.replace(/([A-Z])/g, " $1").replace(/^./, function (match) {
        return match.toUpperCase();
      });
    },
  },
};
</script>

<style scoped>
.themeMetricText {
  color: #319f9f;
  font-weight: bold;
}
.metricsContainer {
  display: flex;
  align-items: center;
  font-size: 40px;
}
.metricsGrid {
  margin: 50px;
}
</style>
