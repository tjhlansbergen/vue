<template>
  <div>{{ digit }}</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class DigitDisplay extends Vue {
  @Prop() private digit!: number; 
}

</script>
