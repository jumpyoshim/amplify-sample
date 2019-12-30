<template>
  <div id="app">
    <button v-on:click="sendEvent">Send event</button>
  </div>
</template>

<script>
import { Analytics } from "aws-amplify";
window.LOG_LEVEL = "VERBOSE";

export default {
  name: "analytics",
  data() {
    return {};
  },
  methos: {
    sendEvent() {
      Analytics.record({
        name: "Button Clicked",
        attributes: {
          AttrName1: "AttrValue1",
          AttrName2: "AttrValue2"
        }
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
