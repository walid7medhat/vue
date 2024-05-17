<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png">
<h1>Sign Up</h1>
<div class="register">
<input type="text" placeholder="enter name">
<input type="text" placeholder="enter Email">
<input type="password" placeholder="enter Password">
<button> Sign Up</button>

</div>
</template>
<script>
export default {
    name : 'SignUp'
}
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