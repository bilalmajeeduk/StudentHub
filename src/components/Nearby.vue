<template>
  <Header></Header>
    <div class="forms">
      <form @submit.prevent="NearbyButton">
              <input class="inputs" type="text" placeholder="Enter your address" v-model="coordinates"  />
        <button @click="location" style="margin-left:250px ">click me for  live location</button>
          <div class="fs">
                  <label>Select Place</label>
                <select v-model="type">
                  <option value="restaurant">Restaurant</option>
                  <option value="cinema">Cinema</option>
                  <option value="cafe">Food</option>
                  <option value="night_club">Club</option>
                  <option value="bar">Bar</option>
                  <option value="spa">Spa</option>
                  <option value="casino">Casino</option>
                  <option value="museum">Museum</option>
                  <option value="laundry">Laundry</option>
                  
                </select>
            <label>Select Distance</label>
              <select v-model="radius">
              <option value="3">3 Mile</option>
              <option value="9">9 Mile</option>
              <option value="12">12 Mile</option>
              <option value="15">15 Mile</option>
             </select>
          </div>
        <button style="margin-left:300px" @click="NearbyButton">Find Places</button>
      </form>
    </div>
  <div class="flex-container">
  <div class="l" >
    <ul >
      <li  style="border:2px solid black; cursor: pointer;" v-for="place in places" :key="place.id" >
        <div style="padding: 15px;" v-html="place.name" @click="onPlaceClick(place)"></div>
        <div>{{place.vicinity}}</div>
      </li>
    </ul>

  </div>
    <div  id="googleMap" class="l2">
        <GoogleMap
  api-key="AIzaSyANbYnMBxiVNihgm8LExFpIs0atcDfhXCI"
  style="width: 100%; height: 500px"
  :center="center"
  :zoom="15"
  >
    <Marker :options="{ position: center }" />
    
  </GoogleMap>
      
     
    </div>
  

  </div>

</template>


<script>
import axios from "axios"
import { defineComponent } from 'vue'
import { GoogleMap, Marker } from 'vue3-google-map'
import Header from "@/components/Header";

export default {
  components: {Header, GoogleMap, Marker },
  data() {
    return{
      type: "",
      radius: "",
      lat: 0,
      lng:0,
      places:[],
    }
  },
  computed: {
    coordinates() {
      return `${this.lat}, ${this.lng}`;
      
    },
      center() {
      return {lat: this.lat, lng: this.lng};
    }
  },
  methods: {
    location() {
      navigator.geolocation.getCurrentPosition(
          position => {
            this.lat = position.coords.latitude;
            this.lng = position.coords.longitude;
          },
          error => {
            console.log("Error getting location");
          }
      );
    },
    onPlaceClick(place){
      console.log({place});
      console.log(place.geometry.location);
      this.lat = place.geometry.location.lat;
      this.lng = place.geometry.location.lng
    },
    NearbyButton() {
      const URL = `https://cors-anywhere.herokuapp.com/https://maps.googleapis.com/maps/api/place/nearbysearch/json?location=${
          this.lat
      },${this.lng}&type=${this.type}&radius=${this.radius *1000}&key=AIzaSyANbYnMBxiVNihgm8LExFpIs0atcDfhXCI`;
      axios.get(encodeURI(URL))
          .then(response => {
            this.places = response.data.results;
                this.addLocationToGoogleMaps();
          }).catch(error => {
        console.log(error.message);
      });
    },
    addLocationToGoogleMaps() {
      const map = new google.maps.Map(this.$refs['map'],
          {
        zoom: 15,
        center: new google.maps.LatLng(this.lat, this.lng),
        mapTypeId: google.maps.MapTypeId.ROADMAP
      });
      this.places.forEach((place) => {
        const lat = place.geometry.location.lat;
        const lng = place.geometry.location.lng;

        let marker = new google.maps.Marker({
          position: new google.maps.LatLng(lat, lng),
          map: map
        });
      });
    }
  }

}


</script>
<style>
.forms{
  align-content: center;
  padding: 25px 25px;
  width: 40%;
  border-radius: 3px;
  border: 3px solid cornflowerblue;
  margin-left:  400px ;
  margin-top: 35px;
}
.fs{
  padding: 25px 25px;
  margin-left: 100px;
  margin-bottom: 10px;
}
.flex-container{
  display: flex;
  width: 100%;
  height: 500px;
  margin-top: 20px;
  padding: 5px;
}
.l{
  flex: 1;
  float: left;
  padding: 25px 25px;
  border-radius: 3px;
  border: 3px solid cornflowerblue;
  width: 100%;
  height: 100%;

}
.l2{
  flex: 3;
  float: left;
  padding: 25px 25px;
  border-radius: 3px;
  border: 3px solid cornflowerblue;
  width: 100%;

  height: 100%;

}

</style>