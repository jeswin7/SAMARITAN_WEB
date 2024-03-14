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
    <input
      type="text"
      placeholder="Country"
      class="textBox samTheme"
      v-model="formData.country"
    />
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
    />
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
export default {
  data() {
    return {
      formData: {
        fname: "",
        lname: "",
        email: "",
        country: "",
        city: "",
        question: "",
        remote: false
      },
    };
  },
  methods: {
    submitForm() {
      console.log(this.formData);
    },
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
.textBox {
  width: 85%;
  margin-bottom: 40px;
}

.rowTextBox {
  width: 40%;
  margin-bottom: 40px;
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
}
.chkBox {
  color: white;
  margin-bottom: 40px;
}
</style>