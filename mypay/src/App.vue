<template>
  <div id="app">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> | -->
      <!-- <router-link to="/about">About</router-link> -->
      <!-- <router-link to="/mine">mine</router-link> -->
      <!-- <router-link to="/volunteer">volunteer</router-link> -->
    </div>
    <router-view/>
    <van-tabbar route>
    <van-tabbar-item replace to="/" icon="home-o">
    首页
    </van-tabbar-item>
    <van-tabbar-item replace to="/about" icon="search">
    心愿单
    </van-tabbar-item>
    <van-tabbar-item replace to="/volunteer" icon="friends-o">
    志愿服务
    </van-tabbar-item>
    <van-tabbar-item replace to="/mine" icon="setting-o">
    账号管理
    </van-tabbar-item>
    </van-tabbar>
  </div>
  
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
