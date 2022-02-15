<template>
 <div class="header">
   <div class="inner_header">
     <router-link to="/"><div class="logo"><h1>Student<span>Hub</span></h1></div></router-link>
     <div class="navigation">
       <router-link to="Accomodations">
         <li>Accomodation</li>
       </router-link>
       <router-link to="jobs">
         <li>Jobs</li>
       </router-link> <router-link to="places2">
       <li>Entertainment</li>
     </router-link> <router-link to="expense">
       <li>Manage Expense</li>
       </router-link>
     </div>
   </div>
 </div>

</template>

<script>
 export default {
  data() {
    return {
      title: 'Student Hub',
    }
  }
}
</script>

<style>
 *{
   margin: 0px;
   padding: 0px;
   list-style: none;
   text-decoration: none;
 }
 .header{
    width: 100%;
    height: 80px;
    background-color: black;
    display: block;
 }
  .inner_header{
    width: 1000px;
    height: 100%;
    background-color: black;
    display: block;
    margin: 0 auto;
  }
  .logo{
    height: 100%;
    display: table;
    float: left;
  }
  .logo h1{
    color: antiquewhite;
    height: 100%;
    display: table-cell;
    vertical-align: middle;
    font-family: "American Typewriter";
    font-size: 32px;
    font-weight: 200;
  }
  .logo span{
    font-weight: 800;
  }
  .navigation{
    float: right;
    height: 100%;
  }
  .navigation a{
    float: left;
    height: 100%;
    padding: 0px 20px;
    display: table;
  }
  .navigation a:last-child{
  padding-right: 0px;
  }
  .navigation li{
    vertical-align: middle;
    display: table-cell;
    color: antiquewhite;
    height: 100%;
    font-size: 16px;
    font-family: "American Typewriter";
    cursor: pointer;

  }

</style>

<!--header{-->
<!--background-color: cornflowerblue;-->
<!--color: black;-->
<!--height: 50px;-->
<!--text-align: left;-->
<!--}-->