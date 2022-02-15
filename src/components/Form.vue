<template>
  <form @submit.prevent="detailsHandler">
      <input type="text" placeholder="Add your expense" v-model="details.exp">
    <input type="number" placeholder="add money" v-model="details.value">
    <input type="date" placeholder="select date" v-model="details.date">
    <input type="submit" value="SUBMIT">
  </form>
</template>

<script>
  import { reactive } from "vue";
  export default {
      props: {
        state: Object,
      },
    setup(props, {emit}) {
        const details = reactive({
          exp : null,
          value: null,
          date: null,
        });
        function detailsHandler () {
          emit("add-expense",{
            exp: details.exp,
            value: details.value,
            date: details.date
          });
          details.exp = null;
          details.value= null;
          details.date = null;
      }
      return {
          detailsHandler,
          details,
      }
    }
  }

</script>

<style scoped>
form {
  border-radius: 2px !important;
  margin-top: 40px;
  display: flex;
  justify-content: center;
  background-color: #666666;
}
form input {
  font-size: 18px;
}
form input::placeholder {
  color: #666666;
}
form input:not([type="submit"]) {
  display: block;
  background: #FFF;
  padding: 5px 15px;
}
form input[type="submit"] {
  display: block;
  color: black;
  padding: 7px 17px;
  background-color: wheat;
  cursor: pointer;
}
</style>