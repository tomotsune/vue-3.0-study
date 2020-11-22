<template>
  <div>
    <h3 :style="{color:colorRef}">孙组件</h3>
  </div>
</template>

<script>
import {inject} from "@vue/runtime-core";

export default {
  name: "11. grandson",
  setup() {
    const color = inject('color');
    const colorRef = inject('colorRef');
    return {
      color,
      colorRef
    }
  }
}
</script>

<style scoped>

</style>
