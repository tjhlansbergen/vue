<template>
  <div id="app">
    <div class="overlay" v-show="overlay">"overlay"</div>
    <DigitDisplay :digit=digit class="left" />
    <DigitPicker :digit=digit class="right" v-on:clickerClicked="match($event)" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import DigitDisplay from './components/DigitDisplay.vue';
import DigitPicker from './components/DigitPicker.vue';

@Component({
  components: {
    DigitDisplay,
    DigitPicker
  },
})
export default class App extends Vue {
  digit = Math.floor(Math.random() * (10))
  overlay = false

  match(dig: number): void{
      if(dig == this.digit){
        this.overlay = true
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-size: 40px;
  color: #2c3e50;
  margin: 40px;
}

.overlay {
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  background-color: red;
}

.right {
  float: right;
}

.left {
  float: left;
}

.clicker {
  cursor: pointer;
  border: 3px solid darkgoldenrod;
}

.clicker:hover {
  border: 3px solid black;
}

</style>
