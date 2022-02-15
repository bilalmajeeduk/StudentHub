<template>
  <h1 style="text-align: center; margin-top:50px; color: cornflowerblue">Register your account to our PLATFORM</h1>
  <div class="signup">
    <form @submit.prevent="SignUp">
      <label>Email:</label>
      <input type="text" placeholder="Type Your EMAIL" v-model="email"/>
      <label>Password:</label>
      <input type="password" placeholder="Type your password" v-model="password"/>
      <input type="submit"  value="Register"/>

    </form>

  </div>
  <h3 style="margin-left: 90px">Already have an account<router-link to="/login"> login here</router-link> </h3>
</template>
<script>
import firebase  from 'firebase';
import {ref} from "vue";

export default{
    setup() {
          const email = ref("");
          const password = ref("");

          const SignUp= () =>{
            firebase
              .auth()
              .createUserWithEmailAndPassword(email.value, password.value)
              .then(user =>{
                alert(user)
            })
            .catch(err => alert(err.message))
      }
      return {
            SignUp,
            email,
            password
      }
    }

}


</script>

<style>
.signup{
  align-content: center;
  margin: 100px 600px;

}
.loginForm{

}
input {
  height: 40%;
  width: 100%;
  box-sizing: border-box;
  padding: 15px 15px;
  margin: 10px ;
}
label{
  margin-left: 10px;
  color: cornflowerblue;
}
</style>