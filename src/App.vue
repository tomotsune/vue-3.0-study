<template>
  <div id="app">
    <!--<comp-setup msg="welcome"/>-->
    <!--<comp-reactive/>-->
    <!--<comp-ref/>-->
    <!--<CompComputed/>-->
    <!--<comp-readonly/>-->
    <!--<comp-watch/>-->
    <!--<comp-effect/>-->
    <!--<comp-tools/>-->
    <!--<comp-lifecycle/>-->
    <!--<h1>父组件</h1>
    <button @click="colorRef='red'">red</button>
    <button @click="colorRef='yellow'">yellow</button>
    <button @click="colorRef='blue'">blue</button>
    <hr>
    <comp-son/>-->
    <comp-refs/>
  </div>
</template>

<script>
import CompSetup from './components/01.setup'
import CompReactive from "./components/02.reactive";
import CompRef from "./components/03.ref";
import CompComputed from "./components/04.computed";
import CompReadonly from "./components/05.readonly";
import CompWatch from "./components/06.watch";
import CompEffect from "./components/07.watchEffect";
import CompTools from "./components/08.tools";
import CompLifecycle from "./components/09.lifecycle";
import CompSon from "./components/10.son";
import CompRefs from "./components/12.refs";

import {provide} from "@vue/runtime-core";
import {ref} from "@vue/reactivity";


export default {
  name: 'App',
  components: {
    CompSetup,
    CompReactive,
    CompRef,
    CompComputed,
    CompReadonly,
    CompWatch,
    CompEffect,
    CompTools,
    CompLifecycle,
    CompSon,
    CompRefs
  },
  setup() {
    /**
     * 向后代传递数据
     */
    //不具有响应式
    provide('color', 'pink');
    //具有响应式
    const colorRef = ref('red');
    provide('colorRef', colorRef);
    return {
      colorRef
    }
  }
}
</script>

<style>
#app {

}
</style>
