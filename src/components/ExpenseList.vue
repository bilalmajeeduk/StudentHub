<template>
    <div class="expenseList">
      <ExpenseDetails v-for="data in state.expense" :key="data.id" :expense="data" />

    </div>
</template>

<script>
import ExpenseDetails from "@/components/ExpenseDetails";
export default {
  components: {ExpenseDetails},
  props: {
      state: Object,
    },
  setup() {
    return {
      ExpenseDetails
    }
  }
}

</script>


<style scoped>
  .expenseList {
    margin-top: 35px;
    padding: 20px;
  }
</style>