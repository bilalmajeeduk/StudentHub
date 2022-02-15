<template>
  <Header></Header>
  <div class="ad">
    <img src="/src/assets/nhs.png" alt="nhs" style="width:128px" height="128px">
  <h3 style="font-size: 28px; color: #FFFFFF">  You need to register with a a GP. It is best to register with local GP.</h3>
  <p style="font-size: 18px; text-align: center"> What is GP? : In the medical profession, a general practitioner is a medical doctor who treats acute and chronic illnesses and provides preventive care and health education to patients</p>
    <div class="applis">
      <p> Apply yor National Insurance Number <a href="https://www.gov.uk/apply-national-insurance-number">here</a>   </p>
    </div>

    <div class="ads">
      <label style="margin-top:40px; color:yellow; font-weight: bold;"  >STEP 1 </label>
    <p> Any student can register with the GP, it is totally free.</p>
    <p> Find a GP in your local area <a  href="https://www.nhs.uk/service-search/find-a-gp">Here</a> </p>

    </div>
    <div class="appli">
      <label style="color:yellow; font-weight: bold;">STEP 2 </label>
      <p> Select GP and register online on their website, <br>later you will receive a letter with your NHS number </p>
    </div>
      <div class="appli">
        <p>You can even Downlaod the nhs app <br> available for both Android and iOS </p>
      </div>

  </div>

</template>

<script>
import Header from "@/components/Header";
export default {
  components: {Header}
}
</script>

<style>
aaa {
  align-content: center;
  font-size: 14px;
  color: greenyellow;
}
aaa:hover {
 color: whitesmoke;
}
.ad {
    background-color: cornflowerblue;
    color: ghostwhite;
    border: 3px solid ghostwhite;
    padding: 30px 30px;

}
.ads{
  background-color: rgb(0, 94, 184);
  border: 2px solid #666666;
  height: 100%;
  width: 25%;
  box-sizing: border-box;
  margin: 40px 40px;
  padding: 15px 15px;
}
 .appli {
   background-color:rgb(0, 94, 184);
   border: 2px solid #666666;
   height: 100%;
   width: 25%;
   box-sizing: border-box;
   margin: 40px 40px;
   padding: 15px 15px;
 }
.applis {
  background-color:rgb(0, 94, 184);
  border: 2px solid #666666;
  height: 100%;
  width: 25%;
  box-sizing: border-box;
  margin: 40px 40px;
  padding: 15px 15px;
  float: right;
}
</style>
