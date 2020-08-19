<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <sandbox>

      <VueAdblockAlert :msg="'awdawd'"/>

    </sandbox>
  </div>
</template>

<script>
import { Sandbox } from 'component-fixture'
import "font-awesome/css/font-awesome.css";
import "component-fixture/dist/ComponentFixture.css";
import VueAdblockAlert from '@/components/VueAdblockAlert.vue'

export default {
  name: 'App',
  components: {
    Sandbox,
    VueAdblockAlert
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
