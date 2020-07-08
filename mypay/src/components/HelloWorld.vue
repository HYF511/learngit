<template>
  <div class="hello">
  <van-grid clickable :column-num="1" icon-size=100px direction=horizontal >
  <van-grid-item icon="manager-o" text="推荐好人" to="/" />
  <van-grid-item icon="label-o" text="文明资讯" to="/" />
  <van-grid-item icon="tv-o" text="服务视听" to="/" />
  <van-grid-item icon="home-o" text="新闻动态" to="/" />
  </van-grid>
  </div>
</template>

<script>
import Vue from 'vue';
import { Grid, GridItem } from 'vant';

Vue.use(Grid);
Vue.use(GridItem)
export default {
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
