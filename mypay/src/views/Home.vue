<template>
  <div class="home">
    
    <rollart/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import rollart from '@/components/rollart.vue'
import HelloWorld from '@/components/HelloWorld.vue'
import Vue from 'vue';
import { Tabbar, TabbarItem } from 'vant';
Vue.use(Tabbar);
Vue.use(TabbarItem);
export default {
  name: 'Home',
  components: {
    rollart,
    HelloWorld
  },
  data() {
    return {
      active: 0,
    };
  },
}
</script>
