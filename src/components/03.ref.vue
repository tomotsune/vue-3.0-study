<template>
  <div>
    <!--在模板中访问时, 无需通过.value属性, 会自动展开-->
    <p>{{ count }}</p>
    <button @click="count++">修改</button>
    <hr>

    <button @click="change"></button>
  </div>
</template>

<script>
import {ref, reactive} from "vue";

export default {
  name: "03.ref",
  setup() {
    // 创建响应式数据对象count, 初始值为1
    const count = ref(1);
    // 必须通过.value
    console.log(count.value);

    const data = reactive({
      count
    });
    // 此处也不需..
    console.log(data.count);
    // 各处都会改变, 相互关联
    data.count = 6;
    console.log(count.value)

    /**
     * 定义方法
     */
    const change = () => {
      ++count.value;
    }
    return {
      count,
      change // 必须返回才能被外部访问
    }
  }

}
</script>

<style scoped>

</style>
