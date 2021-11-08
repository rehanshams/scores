<template>
  <div class="league">
    <div class="info">
      <div class="country">
        <img :src="'https://flagcdn.com/w20/'+league.country.code+'.png'" /> 
        <span>
          &nbsp;{{league.country.name}} - 
          <strong class="name">{{league.name}}</strong>
        </span>
      </div>
      <div class="favorite" @click="setFav">
        <font-awesome-icon :icon="[league.isFav ? 'fas':'far', 'star']" :style="{ color: '#358d84' }" />
      </div>
    </div>
    <Matches :matches="league.matches" />
  </div>
</template>

<script>
import Matches from './Matches.vue'
export default {
  name: 'League',
  components: {
    Matches
  },
  props: {
    league: Object
  },
  methods: {
    setFav(evt){
      if(this.league.isFav){
        this.league.isFav = false
        evt.target.parentNode.innerHTML = '<i class="far fa-star" color="#358d84"></i>'
      }else{
        this.league.isFav = true
        evt.target.parentNode.innerHTML = '<i class="fas fa-star" color="#358d84"></i>'
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.league{
  background: #fff;
}
.info{
  color: #333;
  padding: 10px;
  display: flex;
  font-size: 14px;
  font-weight: 400;
  align-items:baseline;
  flex-flow: row nowrap;
  justify-content:space-between;
}
.country span{
  top: -1px;
  position: relative;
}
.info div{
  display: inline-block;
}
</style>
