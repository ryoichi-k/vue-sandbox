<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Slot>
    <template v-slot:name>junnnosuke</template>
    <template v-slot:sex></template>
  </Slot>
  <Test message="テストだよ" x="トートバッグ" />
  <HelloWorld msg="Hello Vue 3 in CodeSandbox!" />
</template>

<script>
import HelloWorldVue from "./components/HelloWorld.vue";
import TestVue from "./components/Test.vue";
import SlotVue from "./components/Slot.vue";
export default {
  name: "App",
  components: {
    HelloWorld: HelloWorldVue,
    Test: TestVue,
    Slot: SlotVue,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
