<template>
  <Header></Header>
  <div class="ad">
    <h3 style="font-size: 28px; color: #FFFFFF">These are some best and verified Financial Aid Websites. </h3>
    <div class="applis">
      <p> Fees and financial support <a href="https://www.internationalstudents.cam.ac.uk/applying/fees-and-financial-support">here</a>   </p>
    </div>

    <div class="ads">
      <label style="margin-top:40px; color:yellow; font-weight: bold;"  >Web 1 </label>
      <p>This is british council website, which provide scholarship and funding <a  href="https://study-uk.britishcouncil.org/scholarships">Here</a>  </p>
    </div>
    <div class="appli">
      <label style="color:yellow; font-weight: bold;">Web 2 </label>
      <p> This web provide Financial aid to international students <a href="https://www.internationalstudent.com/study_uk/financial_aid/">Here</a>  </p>
    </div>
    <div class="appli">
      <label style="color:yellow; font-weight: bold;">Web 3 </label>
      <p> Scholarships to Study in UK: Types, Application, Eligibility, Award
        <a href="https://collegedunia.com/uk/article/financial-support-for-international-students-to-study-in-the-uk-scholarships-student-loans-international-organizations">Here</a>  </p>
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
