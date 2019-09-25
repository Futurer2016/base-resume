<template>
<header class="clearfix">
  <div class="my-img">
    <img src="./../assets/img/head.jpg" alt="">
  </div>
  <div class="my-info">
    <h1 class="my-name small-title">{{ myName }}</h1>
    <div class="my-base-info">
      <ul class="clearfix">
        <li class="info-box" v-for="({label, desc}, index) in baseInfos" :key="index">
          <span class="info-title">{{ label }}</span>
          <span class="info-desc">{{ desc }}</span>
        </li>
      </ul>
    </div>
  </div>
</header>
</template>

<script>
import info from '@/data/info.js'

export default {
  data() {
    let baseInfos = [
      {label: '性别', desc: 'xx'},
      {label: '生日', desc: 'xxxx.xx.xx'},
      {label: '籍贯', desc: 'xxxx'},
      {label: '学历', desc: 'xxx'},
      {label: '英语', desc: 'CET-4'},
      {label: '联系电话', desc: 'xxx xxxx xxxx'},
      {label: '邮箱', desc: 'xxxxx@qq.com'}
    ];
    return {
      myName: info.myName || 'Lorem.',
      baseInfos: info.headInfo || baseInfos
      // baseInfos
    }
  }
}
</script>

<style lang="scss">
.my-img {
  float: right;
  margin-left: 10px;
  height: 200px;
  box-shadow: 0 1px 3px #000;
  img {
    height: 100%;
  }
}
.my-info {
  overflow: hidden;
  padding-left: 40px;
  .my-name {
    position: static;
    line-height: 3;
    font-size: 30px;
  }
  .my-base-info {
    line-height: 1.6;
    .info-box {
      float: left;
      width: 400px;
      .info-title {
        display: inline-block;
        padding-right: 2px;
        width: 75px;
        text-align-last: justify;
      }
      .info-desc {
        position: relative;
        padding-left: 10px;
        &::before {
          content: ":";
          position: absolute;
          left: 0;
        }
      }
    }
  }
}
</style>
