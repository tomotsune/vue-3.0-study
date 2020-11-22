<template>
  <div>
    <p>{{msg}}</p>
  </div>
</template>

<script>
import {ref} from "@vue/reactivity";

export default {
  name: "13.compRef",
  setup() {
    const msg = ref('welcome');

    const change = () => {
      msg.value = "欢迎";
    }

    return {
      msg,
      change
    }
  }
}
</script>

<style scoped>

</style>
