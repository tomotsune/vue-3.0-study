<template>
  <div>
    <input type="text" v-model="keywords">
  </div>
</template>

<script>
import {watch, ref} from "vue";

export default {
  name: "06.watch",
  setup: function () {

    const keywords = ref('');
    //定义一个函数, 用来异步执行打印任务, 返回对应的计时器
    const print = value => {
      return setTimeout(() => {
        console.log(value);
      }, 1000);
    };
    watch(keywords, (to, from, clean) => {
      let timer = print(to);

      /**
       * 参数clean是一个用来清理无效异步任务的函数.
       * 当出现以下情况时, 会自动触发执行clean函数, 用来清理无效的异步任务, 即上次还未执行的异步任务
       *  1. 当前监视器即将重新执行时
       *  2. 当监视器被停止时.
       */
      //传入一个回调
      clean(()=>{
        clearTimeout(timer);// 停止上次还未执行完成的异步任务
      });
    });
    return {
      keywords
    }
  }
}
</script>

<style scoped>

</style>
