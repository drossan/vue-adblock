<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <sandbox>

      <VueAdblock :msg="'awdawd'"/>

    </sandbox>
  </div>
</template>

<script>
import { Sandbox } from 'component-fixture'
import "font-awesome/css/font-awesome.css";
import "component-fixture/dist/ComponentFixture.css";
import VueAdblock from '@/components/VueAdblock.vue'

export default {
  name: 'App',
  components: {
    Sandbox,
    VueAdblock
  }
}
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
