<template>
  <div class="leagues" v-for="league in leagues" :key="league.id">
    <League :league="league" />
  </div>
</template>

<script>
import League from './League.vue'
export default {
  name: 'Leagues',
  components: {
    League
  },
  props: {
    leagues: Array
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.leagues{
  overflow: hidden;
  border-radius: 4px;
  background: #fff;
  margin-bottom: 15px;
  border: 1px #ddd solid;
  box-shadow: 1px 1px 4px #eee;
}
</style>
