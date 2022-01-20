<template>
  <div>
    <div v-on:click="$emit('clickerClicked', digit)" class="clicker">
      <div v-for="x in range" :key=x>
        &#11088;
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class DigitClicker extends Vue {
  @Prop() private digit!: number; 
  range = [...Array(this.digit).keys()]
}

</script>
