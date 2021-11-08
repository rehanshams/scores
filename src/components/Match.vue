<template>
  <div class="match">
      <div class="status">
          <span>{{match.isEnd ? 'End':'Start'}}</span>
          <br/>
          <span>{{match.isPens ? 'Pens':''}}</span>
      </div>
      <div class="teams">
        <div class="team teamA" :style="match.teamA.score > match.teamB.score ? 'font-weight:600':''" >

            <span class="name">{{match.teamA.name}}</span>
            <span class="score">{{match.teamA.score}}</span>
        </div>
        <div class="team teamB" :style="match.teamA.score < match.teamB.score ? 'font-weight:600':''">
            <div class="name">{{match.teamB.name}}</div>
            <div class="score">{{match.teamB.score}}</div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Match',
  props: {
    match: Object
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.match{
  display: flex;
  border-radius: 4px;
  align-content: center;
  align-items: center;
  flex-flow: row nowrap;
  justify-content:space-between;
}
.status{
    color: #999;
    padding: 8px 0;
    font-size: 13px;
    font-weight: 600;
    text-align: center;
}
.teams{
    width: 100%;
    padding: 2px 20px;
}
.team{
  display: flex;
  padding: 2px 0;
  align-content: center;
  align-items: baseline;
  flex-flow: row nowrap;
  justify-content:space-between;
}

</style>
