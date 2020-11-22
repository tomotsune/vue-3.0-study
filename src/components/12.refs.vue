<template>
  <div>
    <h3 ref="h3Ref">嘿嘿</h3>
    <hr>
    <com-ref ref="compRef"/>
  </div>
</template>

<script>
import {ref} from "@vue/reactivity";
import {onMounted} from "@vue/runtime-core";
import ComRef from './13.compRef';

export default {
  name: "12.refs",
  setup() {
    /**
     * 引用元素
     * @type {null}
     */
        // 创建一个值为null的ref, 实践上就是一个引用
    const h3Ref = ref(null);

    /**
     * 引用组件
     */

    const compRef = ref(null);

    //等待页面渲染完成(onMounted)
    onMounted(() => {
      console.log(h3Ref.value);// DOM元素
      h3Ref.value.style.color = 'red';

      console.log(compRef.value);
      compRef.value.change();
    });

    return {
      h3Ref,
      compRef
    }
  },
  components: {
    ComRef
  }
}
</script>

<style scoped>

</style>
