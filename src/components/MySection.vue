<template>
<section class="sec">
  <div class="sec-line"></div>
  <h2 class="sec-title">{{ secs.title }}</h2>
  <div class="sec-main">
    <my-subject v-for="(parDesc, index) in secs.list" :key="index" :parDesc="parDesc"></my-subject>
  </div>
</section>
</template>

<script>
import MySubject from './MySubject'

export default {
  props: ['secs'],
  components: {
    MySubject
  }
}
</script>

<style lang="scss">
@import './../assets/css/common/vars.scss';
.sec {
  padding-bottom: 10px;
  .sec-line {
    margin-top: 5px;
    border-top: 5px dashed $blue;
  }
  .sec-title {
    float: left;
    margin-top: -5px;
    box-sizing: border-box;
    padding: 5px 0;
    width: 120px;
    text-align: center;
    color: #fff;
    background-color: $blue;
  }
  .sec-main {
    // overflow: hidden;
    margin-left:  120px;
  }
}

</style>
