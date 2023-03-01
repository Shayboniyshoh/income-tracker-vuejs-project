<template>
  <div id="app">
    <HeaderItem :totalIncome="state.totalIncome" />
    <FormFields @add-income="AddIncome" />
  </div>
</template>

<script>
import { reactive, computed } from "vue";
import HeaderItem from "./components/HeaderItem.vue";
import FormFields from "./components/FormFields.vue";

export default {
  components: { HeaderItem, FormFields },
  setup() {
    const state = reactive({
      income: [],
      totalIncome: computed(() => {
        let temp = 0;
        if (state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].price;
          }
        }
        return temp;
      })
    });
    function AddIncome(data) {
      let d = data.date.split("-");
      let newD = new Date(d[0], d[1], d[2]);

      state.income = [...state.income, {
        id: Date.now(),
        desc: data.desc,
        price: parseInt(data.price),
        date: newD.getTime()
      }]
      console.log(state.income);
    }

    return {
      HeaderItem,
      FormFields,
      state,
      AddIncome
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #eee;
}
</style>
