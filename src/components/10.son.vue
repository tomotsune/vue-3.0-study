<template>
  <div>
    <h2>子组件</h2>
    <hr>
    <comp-grandson/>
  </div>
</template>

<script>
import CompGrandson from "./11. grandson";

export default {
  name: "10.son",
  components: {
    CompGrandson
  },
  setup() {


    return {}
  }
}
</script>

<style scoped>

</style>
