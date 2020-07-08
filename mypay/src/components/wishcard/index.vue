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
    v-model="username"
    name="姓名"
    label="姓名"
    placeholder="姓名"
    :rules="[{ required: true, message: '请填写姓名' }]"
    />
   <van-field
    v-model="password"
    type="password"
    name="电话"
    label="电话"
    placeholder="电话"
    :rules="[{ required: true, message: '请填写电话' }]"
    />
    <van-field
    v-model="wish"
    name="心愿"
    label="心愿"
    placeholder="心愿"
    :rules="[{ required: true, message: '请填写心愿' }]"
    />
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
<van-field
  readonly
  clickable
  name="area"
  :value="value1"
  label="地区选择"
  placeholder="点击选择省市区"
  @click="showArea = true"
/>
<van-popup v-model="showArea" position="bottom">
  <van-area
    :area-list="areaList"
    @confirm="onConfirm1"
    @cancel="showArea = false"
  />
</van-popup>
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
Vue.use(Calendar);
import { Form } from 'vant';
import { Field } from 'vant';
import { DatetimePicker } from 'vant';
import { Area } from 'vant';

Vue.use(Area);
Vue.use(NavBar);
Vue.use(DatetimePicker);
Vue.use(Field);

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
      showArea: false,
      areaList: {
  province_list: {
    110000: '北京市',
    120000: '天津市'
  },
  city_list: {
    110100: '北京市',
    110200: '县',
    120100: '天津市',
    120200: '县'
  },
  county_list: {
    110101: '东城区',
    110102: '西城区',
    110105: '朝阳区',
    110106: '丰台区',
    120101: '和平区',
    120102: '河东区',
    120103: '河西区',
    120104: '南开区',
    120105: '河北区',
    // ....
  }
}, // 数据格式见 Area 组件文档
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

    onConfirm1(values) {
      this.value1 = values.map((item) => item.name).join('/');
      this.showArea = false;
    },
    onClickRight() {
      Toast('返回');
    },
    
  }
}
</script>