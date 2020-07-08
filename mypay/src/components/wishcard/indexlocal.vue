<template>
  <div class="local">
    <van-form @submit="onSubmit">
  <van-field
  readonly
  clickable
  name="area"
  :value="value"
  label="心愿投放地"
  placeholder="点击选择省市区"
  @click="showArea = true"
    />
<van-popup v-model="showArea" position="bottom">
  <van-area
    :area-list="areaList"
    @confirm="onConfirm"
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
import { Area } from 'vant';

Vue.use(Area);
export default {
  data() {
    return {
      value: '',
      showArea: false,
      areaList: {}, // 数据格式见 Area 组件文档
    };
  },
  methods: {
    onConfirm(values) {
      this.value = values.map((item) => item.name).join('/');
      this.showArea = false;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
