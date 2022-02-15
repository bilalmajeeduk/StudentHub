<template >
  <Header></Header>
    <div class="grid grid-cols-3 ">
  <div style="cursor:pointer;"
       class="gap-4"
  v-for="room in rooms">
    <a :href="room.page">
    <div class="card-inner" >

      <div class="card-image-wrap" >
        <img v-bind:src ="room.srcTxt" class="image"/>
      </div>
      <div>
        <h2 class="titles" >{{room.rawTxt}}</h2>
      </div>
      <div class="card-details">
          <h2 >{{room.price}}</h2>
        <p>
          {{room.address}}
        </p>
      </div>
    </div>
    </a>
  </div>
    </div>
</template>


<script>
import Vue from 'vue'
import db from '@/main';
import Header from "@/components/Header";
require('@/assets/styles.css')

export default  {
  components: {
    Header,
  },
  data() {
    return{
      rooms: [


      ]
    }
  },
  methods: {
      pageLoad() {
        this.rooms.forEach(room => {
          db.collection('rooms').add(room)
        })
      },
    getData(){
      db.collection('rooms')
          .get()
          .then(querySnapshot => {
            this.rooms = querySnapshot.docs.map(doc => doc.data())

          })
    }
  },
  created(){
    this.getData();
  }
  /*
  const ListRendering = {
    data() {
      return{
        studentRooms:[
          {
            price: '£225 Per week',
            srcTxt: 'https://assets2.unilodgers.com/cdn-cgi/image/width=850,height=555,dpr=1,quality=70,format=auto/uploads/property/1625030870_CubeGreenwich_CommunalSpace6.jpg',
            rawTxt: 'The Cube Greenwich',
          },
          {
            price: '£225 Per week',
            srcTxt: 'https://assets2.unilodgers.com/cdn-cgi/image/width=850,height=555,dpr=1,quality=70,format=auto/uploads/property/1625030870_CubeGreenwich_CommunalSpace6.jpg',
            rawTxt: 'The Cube Greenwich',
          },
        ]
      }
    }
}

   */
}

</script>

<style >
</style>