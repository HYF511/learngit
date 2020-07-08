<template>
<nav>
  <van-nav-bar
  title="标题"
  left-text="返回"
  right-text="按钮"
  left-arrow
  @click-left="onClickLeft"
  @click-right="onClickRight"
/>
</nav>
<div>
<van-sidebar v-model="activeKey">
  <van-sidebar-item title="标签名称" />
  <van-sidebar-item title="标签名称" />
  <van-sidebar-item title="标签名称" />
</van-sidebar>
</div>
</template>
<script>


import Vue from 'vue';
import { NavBar, Toast,Sidebar, SidebarItem  } from 'vant';
Vue.use(Sidebar);
Vue.use(SidebarItem);
Vue.use(NavBar);
export default {
   data() {
    return {
      activeKey: 0,
    };
  },
  methods: {
    onClickLeft() {
      Toast('返回');
    },
    onClickRight() {
      Toast('按钮');
    },

  },
  
    
  }
  
   
</script>