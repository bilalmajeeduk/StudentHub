<template>
    <header>
    <h3>Manage your all expense here</h3>
    <div class="total-expense">£{{ totalExpense }}</div>
    </header>
</template>
<script>
import Header from "@/components/Header";
export default {
  props: {
    totalExpense: Number,
  }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 20px;
  border-top: 5px solid dimgray;
  background-color: cornflowerblue;
  border-bottom: 5px solid dimgray;
}
header h3 {
  color: #EEE;
  font-size: 28px;
  margin-left: 500px;
}
header .total-expense {
  background-color: wheat;
  border-radius: 8px;
  min-width: 100px;
  text-align: center;
  font-size: 20px;
  font-weight: 700;
  padding: 5px 10px;
  color: black;
}
</style>