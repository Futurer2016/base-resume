<template>
<div class="sec-p">
  <h3 v-if="parDesc.title" class="sec-p-title small-title">
    {{ parDesc.title }}
  </h3>
  <template v-if="parDesc.list">
    <my-paragraph :list="parDesc.list"></my-paragraph>
  </template>
</div>
</template>

<script>
import MyParagraph from './MyParagraph';

export default {
  props: ['parDesc'],
  components: {
    MyParagraph
  }
}
</script>

<style lang="scss">
@import './../assets/css/common/vars.scss';

.sec-p {
  position: relative;
  margin-top: 20px;
  padding-left: 20px;
}

</style>
