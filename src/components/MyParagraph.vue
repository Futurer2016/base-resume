<template>
<div class="sec-p">
  <h3 class="sec-p-title small-title">
    {{ parDesc.title }}
  </h3>
  <ul>
    <li class="sec-p-item" v-for="(skill, index) in parDesc.list" :key="index">
      <i class="iconfont icon-tuding1" v-if="isMulti"></i>
      <span v-if="isObject(skill)">
        <strong class="sec-p-label" v-if="skill.label">{{ skill.label }}</strong>
        <span :class="{'sec-p-desc': true, 'desc-indent': skill.multi}">{{ skill.desc }}</span>
      </span>
      <span v-else class="sec-p-desc">{{ skill }}</span>
    </li>
  </ul>
</div>
</template>

<script>

export default {
  props: ['parDesc'],
  methods: {
    isObject(val) {
      return val != null && Object.prototype.toString.call(val) == '[object Object]'
    }
  },
  computed: {
    isMulti() {
      return this.parDesc.list.length > 1;
    }
  }
}
</script>

<style lang="scss">
@import './../assets/css/common/vars.scss';

.sec-p {
  padding-left: 20px;
  ul .sec-p-item {
    position: relative;
    &:nth-of-type(even) {
      background-color: #fee;
    }
    // 列表每行前面的图标
    .iconfont {
      margin-right: 10px;
    }
    .sec-p-label {
      padding-right: 10px;
      &::after {
        content: ":";
        padding-left: 2px;
      }
    }
    .desc-indent {
      display: inline-block;
      text-indent: 2em;
    }
  }
}

</style>
