<template>
  <Header></Header>
   <div class="ad">
 <h1 class="inst">Follow these instruction to apply for your Driving Licence</h1>
     <h3 class="applic">
       It costs £34 to apply online. You can pay by MasterCard, Visa, Electron or Delta debit or credit card.
     </h3>
    <div class="appli">
      <label> Requirements for DVLA:  </label>
      <ol>
        <li>
          1: An identity document,passport number and BRB card.
        </li>
        <li>
          2: Addresses where you’ve lived for up to the last 3 years
        </li>
        <li>
          3: You might be asked for additional information, such as your National Insurance number if you know it.
        </li>
        <li>
          4:  You’ll get a confirmation email from DVLA after you’ve applied.
        </li>
        <li>
         5:  Your licence should arrive within one week if you apply online. It may take longer if DVLA need to make additional checks.
        </li>
      </ol>
    </div>
    <p class="appli"> Apply for your driving licence <a href="http://apply-provisional-driving-licence.service.gov.uk/">Here</a> </p>
  </div>

</template>

<script>
import Header from "@/components/Header";
export default {
  components: {Header}
}
</script>

<style>
.inst {
  text-align: center;
  color: cornsilk;
  border: 30px solid black;
  background-color: black;
  width: 60%;
  margin-left: 250px;
}
 h3 {
   text-align: center;
   margin-top: 20px;
   margin-bottom: 20px;
 }
  .b {
    text-align: center;
   margin-bottom: 20px;
   margin-top: 20px;
   list-style-type: circle;
    font-size: 15px;
 }
 aaa {
   align-items: center;
   font-size: 20px;

 }
.ad {
  background-color: cornflowerblue;
  color: ghostwhite;
  border: 3px solid ghostwhite;
  padding: 30px 30px;
}
.appli {
  background-color:rgb(0, 94, 184);
  border: 2px solid #666666;
  height: 100%;
  width: 25%;
  box-sizing: border-box;
  margin: 40px 40px;
  padding: 15px 15px;
  font-size: 20px;

}
.applic {
  background-color:rgb(0, 94, 184);
  border: 2px solid #666666;
  height: 100%;
  width: 25%;
  box-sizing: border-box;
  margin: 40px 40px;
  padding: 15px 15px;
  font-size: 20px;
  float: right;
}
</style>