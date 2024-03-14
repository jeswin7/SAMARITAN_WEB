<template>
  <Form class="samTheme formContainer" @submit.prevent="submitForm">
    <div class="formHeading">
      Reach Out & Kickstart Your Canadian Journey Today!
    </div>
    <br />
    <div class="formSubHeading">
      We will get back to you within 24-48 hours timeframe
    </div>
    <br />
    <input
      type="text"
      placeholder="First Name"
      class="rowTextBox samTheme"
      v-model="formData.fname"
    />
    &nbsp;
    <input
      type="text"
      placeholder="Last Name"
      class="rowTextBox samTheme"
      v-model="formData.lname"
    />
    <br />
    <input
      type="text"
      placeholder="Email"
      class="textBox samTheme"
      v-model="formData.email"
    />
    <br />
    <select id="countrySelect" v-model="formData.country" class="textBox samTheme">
      <option v-for="country in countries" :key="country.alpha3Code" :value="country.name.common">
        {{ country.name.common }}
      </option>
    </select>
    <br />
    <input
      type="text"
      placeholder="City"
      class="textBox samTheme"
      v-model="formData.city"
    />
    <br />
    <textarea
      placeholder="Your Question/Query"
      class="textBox samTheme"
      multiple
      v-model="formData.question"
    ></textarea>
    <br />
    <input type="checkbox" id="remote" name="remote" v-model="formData.remote" class="chkBox"/>
    <label for="remote" class="chkBox">
      I am outside of Canada and want to search remotely</label
    >
    <br />
    <button class="samThemeBtn samTheme">Submit</button>
  </Form>
</template> 

<script>
import axios from 'axios';

export default {
  data() {
    return {
      countries: [],
      formData: {
        fname: "",
        lname: "",
        email: "",
        country: "", // Updated property name
        city: "",
        question: "",
        remote: false
      },
    };
  },
  mounted() {
    this.fetchCountries()
  },
  methods: {
    submitForm() {
      console.log(this.formData);
    },
    async fetchCountries(){
      try{
        const results = await axios.get('https://restcountries.com/v3.1/all')
        console.log('fetched results:', results)
        this.countries = results.data; // Access the data property
      }
      catch{
        console.log('error!!!')
      }
    }
  },
};
</script>

<style scoped>
.samTheme {
  padding: 10px;
  border-radius: 20px;
}
.formContainer {
  background-color: black;
  padding: 20px;
  opacity: 80%;
}
input, textarea {
  background-color: #202020; 
  /* background-color: white; */
  color: white; 
  font-size: 16px; 
  outline: none;
}
.textBox {
  width: 85%;
  margin-bottom: 40px;
  border: 0;
  border: none; 
}

select {
  width: 85%;
  margin-bottom: 40px;
  border: 0;
  height: 40px;
  border-radius: 20px;
  background-color: black;
  color: white
}

.rowTextBox {
  width: 40%;
  margin-bottom: 40px;
  border: 0;
}

.formHeading {
  color: #319f9f;
  font-size: 25px;
  font-weight: bold;
}
.formSubHeading {
  color: white;
}
.samThemeBtn {
  background-color: #319f9f;
  width: 85%;
  color: white;
  border: 0;
}
.chkBox {
  color: white;
  margin-bottom: 40px;
}
</style>
