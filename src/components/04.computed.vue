<template>
  <div>
    <p>{{ count }}</p>
    <p>{{ plusTwo }}</p>

    <!--修改count, plusOne同步改变-->
    <button @click="++count">修改count</button>
    <!--err: plusOne readonly-->
    <button @click="plusTwo=6">修改count</button>
  </div>
</template>

<script>
import {computed, ref} from "vue";

export default {
  name: "04.computed",
  setup() {
    const count = ref(1);

    // 根据count值, 创建一个响应式的计算属性plusOne
    // 传入get函数
    /*const plusOne = computed(() => {
      return count.value + 1;
    });*/
    // 箭头函数只有一行代码, 可以简写为如下
    // const plusOne = computed(() => count.value + 1);

    const plusTwo = computed({
      // 取值函数
      get() {
        console.log('get...');
        return count.value +1;
      },
      // 赋值函数
      /*set: val=>{},*/
      set(val) {
        console.log('set...');
        count.value = val * 2;
      }
    });

    return {
      count,
      plusTwo
    }
  }

}
</script>

<style scoped>

</style>
