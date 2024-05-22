<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png">
<h1>Sign Up</h1>
<div class="register">
<input type="text" v-model="name" placeholder="enter name">
<input type="text" v-model="email" placeholder="enter Email">
<input type="password" v-model="password" placeholder="enter Password">
<button   v-on:click="signUp"> Sign Up</button>

</div>
</template>
<script>
import axios from 'axios';

export default {
    name: 'SignUp',
    data() { 
        return {
            name: '',
            email: '',
            password: ''
        };
    },
    methods: {
        async signUp() {
            try {
                let response = await axios.post('http://localhost:3000/users', {
                    name: this.name,
                    email: this.email,
                    password: this.password
                });
                if (response.status === 201) {
                    localStorage.setItem('user-info', JSON.stringify(response.data));
                    this.$router.push({ name: 'Home' });
                } else {
                    console.log('Unexpected response status:', response.status);
                }
                console.log(response);
            } catch (error) { 
                console.error('Error during sign up:', error);
            }
        }
    },
    mounted() {
        if (localStorage.getItem('user-info')) {
            this.$router.push({ name: 'Home' });
        }
    }

};
</script>

<style>
.logo{
    width: 100px;
    height: 100px;
    margin-top: 10px;
    margin-bottom: 10px;
}
.register input{
    
     width: 300px;
     height: 40px;
     padding-left: 20px;
     display: block;
     margin-bottom: 30px;
     margin-right: auto;
     margin-left: auto;
     border: 1px solid black;
}
.register button{
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    width: 320px;
    height: 40px;
    border: 1px solid black;
    background-color: black;
    color: white;
    margin-right: auto;
    margin-left: auto;
    margin-bottom: 30px;
    cursor: pointer;
    font-size: 18px;
    font-weight: bold;
    border-radius: 10px;
}
</style>