<template>
  <header :style="{background: color}">
    <div class="topnav">
      <a class="icon" @click="onClick()">
        <font-awesome-icon :icon="['fa', 'bars']" /> &nbsp; <strong>Scores</strong>
      </a>
      <div id="links">
        <a href="#news">News</a>
        <a href="#contact">APIs</a>
        <a href="#about">About</a>
      </div>
    </div>
    <div class="search">
      <font-awesome-icon :icon="['fa', 'search']" />
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    color: String
  },
  methods: {
    onClick(){
      var x = document.getElementById("links");
      if (x.style.display === "block") {
        x.style.display = "none";
      } else {
        x.style.display = "block";
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
  width: 100%;
  margin: auto;
  color: white;
  max-width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.topnav {
  overflow: hidden;
  position: relative;
}

.topnav #links {
  display: none;
}

.topnav a {
  color: white;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
  display: block;
}

.topnav a.icon {
  background: none;
  display: block;
  right: 0;
  top: 0;
}

.search {
  padding: 14px 16px;
  color: white;
}
</style>
