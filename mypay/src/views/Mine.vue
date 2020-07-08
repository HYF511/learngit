<template>
  <div class="wishcard">
  <van-nav-bar
  title="我的工作"
  right-text="我的"
  left-text="返回"
  @click-left="onClickRight"
/>

    <van-form @submit="onSubmit">
<van-field
  readonly
  clickable
  name="picker"
  :value="value1"
  label="志愿队名称"
  placeholder="点击选择我的队伍"
  @click="showPicker = true"
/>
<van-popup v-model="showPicker" position="bottom">
  <van-picker
    show-toolbar
    :columns="columns"
    @confirm="onConfirm1"
    @cancel="showPicker = false"
  />
</van-popup>
    
   
  <van-field
  readonly
  clickable
  name="calendar"
  :value="value"
  label="日期"
  placeholder="点击选择日期"
  @click="showCalendar = true"
/>
<van-calendar v-model="showCalendar" @confirm="onConfirm" />
<van-cell-group>
  <van-field v-model="value3" label="文本" placeholder="请输入用户名" />
</van-cell-group>
<div style="margin: 16px;">
    <van-button round block type="info" native-type="submit">
      提交
</van-button>
</div>
</van-form>

  </div>
</template>
<script>
import Vue from 'vue';
import { NavBar } from 'vant';
import { Toast } from 'vant';
import { Calendar } from 'vant';
import { DropdownMenu, DropdownItem } from 'vant';
import { Form } from 'vant';
import { Field } from 'vant';
import { DatetimePicker } from 'vant';
import { Picker } from 'vant';
import { Popup } from 'vant';
import { Button } from 'vant';


Vue.use(Button);
Vue.use(Popup);
Vue.use(Picker);
Vue.use(Calendar);
Vue.use(NavBar);
Vue.use(DatetimePicker);
Vue.use(Field);
Vue.use(DropdownMenu);
Vue.use(DropdownItem);
Vue.use(Form);
// @ is an alias to /src
export default {
   data() {
    return {
      username: '',
      password: '',
      value: '',
      showCalendar: false,
      value1: '',
      columns: ['青年志愿者', '心心相连', '在路上', '正道的光', '行动派'],
      showPicker: false,
      value3: '',
      };
   },
    
  methods: {
    onSubmit(values) {
      console.log('submit', values);
    },
    onConfirm(date) {
      this.value = `${date.getMonth() + 1}/${date.getDate()}`;
      this.showCalendar = false;
    },

    onConfirm1(value1) {
      this.value1 = value1;
      this.showPicker = false;
    },
    onClickRight() {
      Toast('返回');
    },
    
    },
    }
</script>