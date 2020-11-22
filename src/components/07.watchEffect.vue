<template>

</template>

<script>
import {ref, watchEffect} from "vue";


export default {
  name: "07.watchEffect",
  setup() {
    const count = ref(1);

    /**
     * 1. 先立即执行传入的函数(与watch相反).
     * 2. 当函数内依赖的数据发生变化时会再次执行函数
     */
    watchEffect(() => {
      console.log(count.value);
    });

    setTimeout(() => {
      count.value = 6;
    }, 3000);
    return {}
  }
}
</script>

<style scoped>

</style>
