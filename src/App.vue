<template>
  <div id="app">
    <HeaderItem :totalIncome="state.totalIncome" />
    <FormFields />
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
      income: [{
        value: 400,
      }, {
        value: 900,
      }],
      totalIncome: computed(() => {
        let temp = 0;
        if (state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].value;
          }
        }
        return temp;
      })
    })

    return {
      HeaderItem,
      FormFields,
      state
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
