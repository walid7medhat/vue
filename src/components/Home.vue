<template>
<h1>hello user, welcome on home page</h1>
</template>

<script>
export default { 
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Home',
        mounted() {
        if (!localStorage.getItem('user-info')) {
            this.$router.push({ name: 'SignUp' });
        }
    }
}
</script>