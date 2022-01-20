<template>
  <div>
    <div v-for="b in buttons" :key="b">
      <DigitClicker :digit=b v-on:clickerClicked="$emit('clickerClicked', $event)" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import DigitClicker from './DigitClicker.vue';

@Component({
  components: {
    DigitClicker
  },
})
export default class DigitPicker extends Vue {
  @Prop() private digit!: string; 
  buttons = [...Array(10).keys()].sort(() => (Math.random() > .5) ? 1 : -1);
}

</script>
