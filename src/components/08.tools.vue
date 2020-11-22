<template>
  <div>
    <p>{{name}}</p>
    <p>{{age}}</p>
  </div>
</template>

<script>
import {reactive, isRef, ref, unref} from "vue";
import {toRef, toRefs} from "@vue/reactivity";

export default {
  name: "08.tools",
  setup() {
    /**
     * isRef
     */
    const count = ref(1);
    console.log(isRef(count));
    /**
     * unref
     */
    console.log(unref(count))
    /**
     * toRef
     */
    const state = reactive({
      name: 'tom',
      age: 18
    });
    const ageRef = toRef(state, 'age');
    console.log(ageRef.value);
    console.log(state.age);
    /**
     * toRefs
     */
    const stateRef = toRefs(state);
    console.log(stateRef.age.value);
    return {
      ...toRefs(state)
    }
  }
}
</script>

<style scoped>

</style>
