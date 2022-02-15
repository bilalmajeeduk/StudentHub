<template>
      <div class="expense">
        <div class="remove">~~</div>
        <div class="des">{{ expense.exp }}</div>
        <div class="value">£{{ expense.value }}</div>
        <div class="date">{{ formattedDate }}</div>

      </div>

</template>

<script>
  export default {
    props: {
       expense: Object,
    },
    setup(props){
        let date = new Date (props.expense.date);
        let day = date.getDay();
        let month = date.getMonth();
        let year = date.getFullYear();

        let formattedDate = day + "/" + month + "/" + year;

        return {formattedDate};

    },

  }

</script>


<style scoped>
.expense {
  position: relative;
  display: flex;
  padding: 15px 15px 15px 0px;
  background-color: gray;
  border-radius: 3px;
  max-width: 600px;
  margin: 0 auto 30px;
}
.remove {
  color: yellowgreen;
  line-height: 1;
  text-align: center;
  margin: 0 10px;
  font-size: 24px;
}
.des {
  color: whitesmoke;
  flex: 1 1 100%;
  font-size: 24px;
}
.value {
  color: whitesmoke;
  min-width: 100px;
  font-size: 24px;
}
.date {
  color: whitesmoke;
  text-align: right;
  font-size: 24px;
}
</style>