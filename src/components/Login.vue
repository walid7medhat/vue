<template>
      <img class="logo" alt="Vue logo" src="../assets/logo.png">
<h1>Login</h1>
<div class="login">
<input type="text" v-model="name" placeholder="enter name">
<input type="password" v-model="password" placeholder="enter Password">
<button   v-on:click="signUp"> Login</button><br>
<router-link to="/sign-up">
  Sign up
</router-link>
</div>
</template>
<script>
import axios from 'axios';

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Login',
    data() {
        return {
            name: '',
            password: ''
        };
    },
    methods: {
        async login() {
            try {
                // eslint-disable-next-line no-undef
                let response = await axios.post('http://localhost:3000/users', {
                    name: this.name,
                    password: this.password
                });
                if (response.status === 201) {
                   console.log(response);
                } else {
                    console.log('Unexpected response status:', response.status);
                }
                console.log(response);
            } catch (error) {
                console.error('Error during Login:', error);
            }
        }
    },
}

</script>

<style>
.logo{
    width: 100px;
    height: 100px;
    margin-top: 10px;
    margin-bottom: 10px;
}
.login input{
    
     width: 300px;
     height: 40px;
     padding-left: 20px;
     display: block;
     margin-bottom: 30px;
     margin-right: auto;
     margin-left: auto;
     border: 1px solid black;
}
.login button{
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