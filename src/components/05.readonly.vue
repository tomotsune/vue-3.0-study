<template>

</template>

<script>
import {reactive, readonly} from "vue";

export default {
  name: "05.readonly",
  setup() {
    const reactiveData = reactive({
      count: 1
    });
    const proxy = readonly(reactiveData);
    console.log(reactiveData);
    console.log(proxy);

    return {}
  }
}
</script>

<style scoped>

</style>
