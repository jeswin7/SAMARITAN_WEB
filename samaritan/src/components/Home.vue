<template>
  <div class="hello">
    <img :src="logo" class="logo" >
    <div class="brand">{{brand }}</div>

    <Form />
  </div>
</template>

<script>
import Form from './ContactForm.vue'
export default {
  name: 'HelloWorld',
  props: {
    brand: String
  },
  components: {
    Form: Form
  },
  data(){
    return{
      logo: require("../assets/samaritanLogo.png")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  display: flex;
  align-items: center;
}
.logo{
  width: 100px
}
.brand{
  color: #319F9F;
  font-size: 40px;
}
h3 {
  margin: 40px 0 0;
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
</style>
