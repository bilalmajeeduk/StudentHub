<template>
  <Header></Header>
    <div class="home">
      <button class="b" @click="SignOut">SignOut {{username}} </button>
    </div>
  <h1 class="mains">WELCOME TO STUDENT HUB </h1>
  <div class="video">
    <h4>Understand University portal</h4>
    <section>

      <iframe width="560" height="315" src="https://www.youtube.com/embed/pRWA9XoTIJQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </section>
  </div>
  <div class="grid grid-cols-3 ">

      <div  style="cursor:pointer;"
      class="gap-4"
                   v-for="card in cards" :key="card.title" @click="$router.push(card.routeUrl)">

        <div class="card-inner" >
          <div class="card-image-wrap">
            <img v-bind:src ="card.src" class="image" style="width: 400px; height: 200px" />
          </div>
          <div>
            <h2 class="titles" >{{card.title}}</h2>
          </div>
          <div class="card-details">
            <h2 >{{card.bgText}}</h2>
            <p>
              {{card.description}}
            </p>
          </div>
        </div>
      </div>


  </div>

</template>


<script>
import {ref, onBeforeMount} from "vue";
import firebase from "firebase";
import db from "@/main";
import Header from "@/components/Header";
require('@/assets/styles.css')


export default {
  components: {Header},

  data  () {
    return {
      cards: [],
    } },
    methods: {
      pageLoad() {
        this.cards.forEach(homes => {
          db.collection('home').add(homes)
        })
      },
      getData(){
        db.collection('home')
            .get()
            .then(querySnapshot => {
              this.cards = querySnapshot.docs.map(doc => doc.data())

            })
      }
    },
  created(){
    this.getData();
  },
    setup() {
        const username = ref("")
      onBeforeMount(()=> {
        const user = firebase.auth().currentUser;
        if(user) {
          username.value = user.email.split('@')[0];
        }
      });
      const SignOut = () => {
        firebase
        .auth()
        .signOut()
        .then(() =>console.log("youre signout"))
        .catch(err => (alert(err.message)))
      }
       return{
        username,
        SignOut,
       }
    },



}

</script>
.products {
display: flex;
max-width: 1220px;
padding: 25px;
margin: 0px auto;
}

<style>

.home{
  float: right;
  max-width: 1220px;
  padding: 25px;
  margin: 0px auto;
}
.b{
  text-align: center;
  background-color: cornflowerblue;
  color: white;
  padding: 20px 20px;
  border-radius: 20px;
  border: #EEEEEE solid 3px;
}
.mains{
  text-align: center;
  border: 3px solid snow;
  margin: 5px ;
  color: #EEEEEE;
  background-color: cornflowerblue;
  width: 100%;
  border-radius: 10px;
}
.video{
  margin-left: 450px;
  margin-top: 60px;

}
.video h1 {

}


</style>