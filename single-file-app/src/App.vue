<template>
  <div id="app">
    <div>{{ myDataProperty }} &#8594; <input :value="myDataProperty" @input="updateMyProperty($event)"/></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class App extends Vue {
  // Data property
  myDataProperty = 'update me!'

  // Component method
  updateMyProperty ($event: { target: { value: string } }): void {
    this.myDataProperty = $event.target.value
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: whitesmoke;
  background-color: tomato;
  margin-top: 60px;
}
</style>