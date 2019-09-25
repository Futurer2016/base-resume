<template>
  <article id="app">
    <MyHeader/>
    <MyMain/>
  </article>
</template>

<script>
import MyHeader from './views/MyHeader.vue'
import MyMain from './views/MyMain.vue'

export default {
  name: 'app',
  components: {
    MyHeader,
    MyMain
  }
}
</script>

<style lang="scss">
@import url('//at.alicdn.com/t/font_1277801_lmqgc09shs.css');
@import './assets/css/common/reset.css';
@import './assets/css/common/vars.scss';

#app {
  position: relative;
  margin: 40px auto;
  width: 1060px;
  font-size: 16px;
  line-height: 1.4;
  // background-color: #fcc;
}
.small-title {
  position: absolute;
  left: -120px;
  top: 0;
  margin-top: 20px;
  max-width: 120px;
  font-size: 16px;
  font-weight: 700;
  color: $blue;
}
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
</style>
