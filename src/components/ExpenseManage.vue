<template>
  <Header></Header>
  <subHeader :total-expense="state.totalExpense" />
  <Form @add-expense="AddExpense" />
  <ExpenseList :state="state" />

</template>


<script>
import {computed, reactive} from "vue";

import subHeader from "@/components/subHeader";
import Form from "@/components/Form";
import ExpenseList from "@/components/ExpenseList";
import Header from "@/components/Header";

 export default {
   components: {Header, ExpenseList, Form, subHeader},

  setup() {
    const state = reactive({
      expense: [],
      totalExpense: computed(() => {
        let temp = 0;
        if (state.expense.length > 0) {
          for (let i = 0; i < state.expense.length; i++) {
            temp += state.expense[i].value
          }
        }
        return temp;
      })
    });

    function AddExpense(data) {
      let d = data.date.split("-");
      let NewD = new Date(d[0], d[1], d[2]);

      state.expense = [...state.expense, {
        id: Date.now(),
        exp: data.exp,
        value: parseInt(data.value),
        date: NewD.getTime()
      }];
      console.log(state.expense)
    }

    return {
      subHeader,
      Form,
      ExpenseList,
      state,
      AddExpense
    };

  },
}
</script>

<style>

</style>