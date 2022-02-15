<template>
  <Header></Header>
  <div class="inst">
  <h2>These 3 jobs are popular among students.</h2>
  </div>
  <div class="grid grid-cols-3 ">
    <div style="cursor:pointer;"
         class="gap-4"
         v-for="main in mains">
      <a :href="main.page">
      <div class="card-inner">
        <a :href="main.page"></a>
        <div class="card-image-wrap" >
          <img :src="main.srcTxt" class="image"/>
        </div>
        <div>
          <h2 class="titles" >{{main.name}}</h2>
        </div>
        <div class="card-details">
          <h2 >{{main.des}}</h2>
        </div>
      </div>
      </a>
    </div>
  </div>
  <div style="border-bottom: 1px solid #666666; margin: 0 300px"></div>
  <div class="grid grid-cols-3 ">
    <div style="cursor:pointer;"
         class="gap-4"
         v-for="other in otherJobs">
      <a :href="other.page">
        <div class="card-inner">
          <a :href="other.page"></a>
          <div class="card-image-wrap">
            <img :src="other.srcTxt" class="image"/>
          </div>
          <div>
            <h2 class="titles" >{{other.name}}</h2>
          </div>
          <div class="card-details">
            <h2 >{{other.des}}</h2>
          </div>
        </div>
      </a>
    </div>
  </div>
</template>


<script>
import Vue from 'vue'
import db from "@/main";
import Header from "@/components/Header";

require('@/assets/styles.css')

export default  {
  components: {Header},
  data :function() {
    return{
      mains: [],
      otherJobs:[]
    }
  },
  methods:{
    pageLoad() {
      this.mains.forEach(main => {
        db.collection('jobs').add(main)
      })
    },
    getData(){
      db.collection('jobs')
          .get()
          .then(querySnapshot => {
            this.mains = querySnapshot.docs.map(doc => doc.data())
          })
    },
    pageLoad2() {
      this.otherJobs.forEach(other => {
        db.collection('otherJobs').add(other)
      })
    },
    getData2(){
      db.collection('otherJobs')
          .get()
          .then(querySnapshot => {
            this.otherJobs = querySnapshot.docs.map(doc => doc.data())
          })
    }
  },
  created(){
    this.getData();
    this.getData2()
  }
}

</script>

<style >
.inst {
  text-align: center;
  color: cornsilk;
  border: 15px solid darkolivegreen;
  border-radius: 40px;
  background-color: darkolivegreen;
  width: 40%;
  margin:10px 400px;
}
 bottomB{
   border: 20px solid #313131;
 }
</style>