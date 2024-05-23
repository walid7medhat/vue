<template>
    <h1>Login Page</h1>
    <input type="text" v-model="name" placeholder="enter name">
    <input type="password" v-model="password" placeholder="enter Password">
    <button v-on:click="login"> Login </button>
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