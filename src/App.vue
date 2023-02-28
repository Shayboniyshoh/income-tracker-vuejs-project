<template>
  <div id="app">
    <HeaderItem />
  </div>
</template>

<script>
import HeaderItem from "./components/HeaderItem.vue";

export default {
  components: { HeaderItem },
  setup() {
    return {
      HeaderItem
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
