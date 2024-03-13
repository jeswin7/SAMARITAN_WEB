<template>
    <Form class="formContainer" @submit.prevent="submitForm">
        <div class="formHeading">Reach Out & Kickstart Your Canadian Journey Today!</div>
        <br/>
        <div class="formSubHeading">We will get back to you within 24-48 hours timeframe</div>
        <br/>
        <input type="text" placeholder="fname" class="textBox" v-model="formData.fname" />
        <input type="text" placeholder="lname" class="textBox" v-model="formData.lname"/>
        <br />
        <input type="text" placeholder="email" class="textBox" v-model="formData.email"/>
        <br />
        <input type="text" placeholder="country" class="textBox" v-model="formData.country"/>
        <br />
        <input type="text" placeholder="city" class="textBox" v-model="formData.city"/>
        <br />
        <textarea placeholder="question" class="textBox" multiple v-model="formData.question"/>
        <br />
        <button>Submit</button>
    </Form>
</template> 

<script>
    export default {
        data(){
            return {
                formData: {
                    fname: '',
                    lname: '',
                    email: '',
                    country: '',
                    city: '',
                    question: ''
                }
            }
        },
        methods: {
            submitForm(){
                console.log(this.formData)
            }
        }
    }
</script>

<style scoped>
.formContainer{
    background-color: black;
    padding: 20px;
    border-radius: 10px;
}
.textBox {
    padding: 10px;
    border-radius: 10px;
    width: 80%;
}
.btn{
    padding: 20px;
}
.formHeading{
    color: #319f9f;
    font-size: 25px;
}
.formSubHeading{
    color: white;
}
</style>