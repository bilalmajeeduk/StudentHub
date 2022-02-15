<template>
<div class="login">
  <form class="loginForm" @submit.prevent="SignIn">
      <label>Email:</label>
      <input type="text" placeholder="Type Your Registered EMAIL" v-model="email"/> <br>
    <label>Password:</label>
    <input type="password" placeholder="Type your password" v-model="password"/><br>
    <input type="submit"  value="SignIn"/>
  </form>
  <h3 style="border: 1px solid white; background-color: cornflowerblue; color: #EEEEEE;  margin-left: 50px">Create a new account <router-link to="/signup">Here</router-link> </h3>
</div>

</template>


<script>
import firebase from "firebase";
import {ref} from "vue"

export default {

  setup(){
    const email = ref ("")
        const password = ref("")

    const SignIn = () =>{
      firebase
      .auth()
      .signInWithEmailAndPassword(email.value, password.value)
      .then(mes => console.log(mes))
      .catch(err=> alert(err.message))
    }
    return{
      SignIn,
      email,
      password
    }
  }
}


</script>

<style>
.login{
  align-content: center;
  margin: 150px 600px;

}
.loginForm{

}
input {
  height: 40%;
  width: 100% !important;
  box-sizing: border-box;
  padding: 15px 15px;
  margin: 10px ;
}
label{
  margin-left: 10px;
  color: cornflowerblue;

}
</style>