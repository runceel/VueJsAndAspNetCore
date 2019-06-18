<template>
  <div>
    <div v-bind:key="r" v-for="r in this.results">{{ r }}</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  public results?: string[];

  public async created() {
    const r = await fetch('/api/values');
    this.results = await r.json() as string[];
  }
}
</script>
