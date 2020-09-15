<template>
  <div>
    <div v-bind:key="r" v-for="r in this.results">{{ r }}</div>
  </div>
</template>

<script lang="ts">
    import Vue from 'vue';

export default Vue.extend({
    data() {
        return {
            results: [] as string[],
        };
    },
    async created() {
        const r = await fetch(process.env.VUE_APP_APIPATH);
        this.results = await r.json() as string[];
    }
});
</script>
