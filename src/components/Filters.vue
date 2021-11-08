<template>
  <form @change="onChangeFilter()">
  <div class="dayFilter" :style="{background: color}">
    <div class="toggle">
      <input type="radio" name="dayBy" value="yesterday" id="byYesterday" checked="checked" />
      <label for="byYesterday">Yesterday</label>
      <input type="radio" name="dayBy" value="today" id="byToday" />
      <label for="byToday">Today</label>
      <input type="radio" name="dayBy" value="tomorrow" id="byTomorrow" />
      <label for="byTomorrow">Tomorrow</label>
      <label for="calendar" id="calnd"><font-awesome-icon :icon="['fa', 'calendar-alt']" /></label>
    </div>
  </div>
  <div class="categoryFilter">
    <div class="toggle">
      <input type="radio" name="catBy" value="all" id="byAll" checked="checked" />
      <label for="byAll">All</label>
      <input type="radio" name="catBy" value="live" id="byLive" />
      <label for="byLive">Live</label>
      <input type="radio" name="catBy" value="favorites" id="byFavorite" />
      <label for="byFavorite">Favorites</label>
    </div>
  </div>
  </form>
</template>

<script>
export default {
  name: 'Filters',
  props: {
    color: String
  },
  emits: ["apply-filters"],
  methods:{
    onChangeFilter(){
      let filters = {
        dayFilter : document.querySelector('input[name="dayBy"]:checked').value,
        categoryFilter : document.querySelector('input[name="catBy"]:checked').value
      }
      this.$emit('apply-filters', filters)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dayFilter{
  width: 100%;
  z-index: 2;
  padding-top: 20px;
  position: relative;
  box-shadow: 1px 3px 3px #eee;
  background-color: #358d84;
}
.categoryFilter{
  width: 100%;
  background: #ffffff;
  box-shadow: 1px 1px 4px #ddd;
  border-bottom: 1px #d7d2d2 solid;
}
#calnd{
  color: #fff;
  font-size: 24px;
  padding: 0 10px;
}
/* TOGGLE STYLING */
.toggle {
  width: 100%;
  box-sizing: border-box;
  font-size: 0;
  display: flex;
  align-items:baseline;
  flex-flow: row nowrap;
  justify-content:space-between;
}
.toggle input {
  width: 0;
  height: 0;
  position: absolute;
  left: -9999px;
}
.toggle input + label {
  margin: 0;
  width: 33.33%;
  color: #fff;
  padding: 14px 12px 12px 12px;
  box-sizing: border-box;
  position: relative;
  display: inline-block;
  font-size: 14px;
  line-height: 140%;
  font-weight: 500;
  text-align: center;
  text-transform: uppercase;
  box-shadow: 0 0 0 rgba(255, 255, 255, 0);
  /* ADD THESE PROPERTIES TO SWITCH FROM AUTO WIDTH TO FULL WIDTH */
  /*flex: 0 0 50%; display: flex; justify-content: center; align-items: center;*/
  /* ----- */
}
.categoryFilter .toggle input + label {
  color: #333;
  text-transform: capitalize;
  padding: 10px 12px 8px 12px;
}
.toggle input + label:first-of-type {
  border-right: none;
}
.toggle input + label:last-of-type {
  border-left: none;
}
.toggle input:hover + label {
  border-color: none;
}
.toggle input:checked + label {
  background-color: transparent;
  border-bottom: 2px #fff solid;
  z-index: 1;
}
.categoryFilter .toggle input:checked + label {
  border-bottom: 2px #358d84 solid;
}
.toggle input:focus + label {
  outline-offset: 0.45rem;
}
</style>
