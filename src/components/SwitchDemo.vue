<template>
  <div>
    <h1>Switch 组件示例 </h1>
    <Demo :component="Switch1Demo" />
    <Demo :component="Switch2Demo" />
    <Attr :data="data" :tabHeader="tabHeader"/>
  </div>
</template>
<script lang="ts">
import Switch1Demo from './Switch1.demo.vue'
import Switch2Demo from './Switch2.demo.vue'
import tabHeader from './tabHeader'
import Demo from './Demo.vue'
import Attr from './Attr.vue'
import {ref} from "vue";

export default {
  components: {Demo,Attr},
  setup() {
    const data = ref([
      {
        params: 'value',
        desc: '是否选中',
        type: 'boolean',
        select: 'false / true',
        default: 'false',
      },
      {
        params: 'disabled',
        desc: '是否禁用',
        type: 'boolean',
        select: '/',
        default: 'true',
      }
    ])
    return {Switch1Demo,Switch2Demo,data,tabHeader};
  },
};
</script>
<style lang="scss" scoped>
$border-color: #d9d9d9;
.demo {
  border: 1px solid $border-color;
  margin: 16px 0 32px;

  > h2 {
    font-size: 20px;
    padding: 8px 16px;
    border-bottom: 1px solid $border-color;
  }

  &-component {
    padding: 16px;
  }

  &-actions {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;
  }

  &-code {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;

    > pre {
      line-height: 1.1;
      font-family: Consolas, 'Courier New', Courier, monospace;
      margin: 0;
    }
  }
}
</style>