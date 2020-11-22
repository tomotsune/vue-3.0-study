<template>
  <div>
    <p>{{name}}</p>
    <button @click="name='mike'">修改name</button>
  </div>
</template>

<script>
// 1. 导入
import {reactive} from "vue"

export default {
  name: "02.reactive",
  setup() {
    // 2. 创建响应式的数据对象
    const data = reactive({
      name: 'tom',
      age: 18
    })
    console.log(data.name)
    return data;
  }
}
</script>

<style scoped>

</style>
