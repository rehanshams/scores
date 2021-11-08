<template>
  <div class="matches" v-for="match in matches" :key="match.id">
    <Match :match="match" />
  </div>
</template>

<script>
import Match from './Match.vue'
export default {
  name: 'Matches',
  components: {
    Match
  },
  props: {
    matches: Array
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.matches{
  padding: 4px 10px;
  background: #fff;
  border-bottom: 1px #ebebf0 solid;
}

.matches:first-of-type {
  border-right: none;
}
.matches:last-of-type {
  border-bottom: none;
}
</style>
