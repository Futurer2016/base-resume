<template>
<ul class="sec-p-list">
  <li :class="{'sec-p-item': true, 'sec-p-item-single': ! skill.list}" v-for="(skill, index) in list" :key="index">
    <i class="iconfont icon-tuding1" v-if="isMulti(index, list)"></i>
    <template v-if="isObject(skill)">
      <h4 class="sec-p-title" v-if="skill.title">{{ skill.title }}</h4>
      <strong class="sec-p-label" v-if="skill.label">{{ skill.label }}</strong>
      <template v-if="skill.desc">
        <a v-if="skill.isLink" :href="skill.desc" target="_blank" :class="{'sec-p-desc': true, 'desc-indent': skill.multi}">{{ skill.desc }}</a>
        <span v-else :class="{'sec-p-desc': true, 'desc-indent': skill.multi}">{{ skill.desc }}</span>
      </template>
      <!-- 二级 -->
      <template v-if="skill.list">
        <my-paragraph :list="skill.list"></my-paragraph>
      </template>
    </template>
    <span v-else class="sec-p-desc">{{ skill }}</span>
  </li>
</ul>
</template>

<script>

export default {
  name: 'my-paragraph',
  props: ['list'],
  methods: {
    isObject(val) {
      return val != null && Object.prototype.toString.call(val) == '[object Object]'
    },
    isMulti(index, list) {
      let flag = (item) => typeof item == 'string' || item.label || (! item.title && item.desc);
      return list.filter(flag).length > 1;
    }
  }
}
</script>

<style lang="scss">
@import './../assets/css/common/vars.scss';

.sec-p-list {
  line-height: 1.5;
  > .sec-p-item {
    position: relative;
    &.sec-p-item-single:nth-of-type(even) {
      background-color: #fee;
    }
    // 列表每行前面的图标
    .iconfont {
      margin-right: 10px;
    }
    .sec-p-title {
      padding-right: 10px;
      color: $blue;
      font-weight: bold;
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
    .sec-p-desc {
      font-size: 14px;
    }
    a {
      text-decoration: underline;
    }
  }
}

</style>
