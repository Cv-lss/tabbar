<template>
  <div class="my-tab-bar">
    <div class="tab-item" v-for="item, index in list" :key="index" :class="{ current: current == index }"
      @click="clickFn(index)">
      <!-- 图标 -->
      <span class="iconfont" :class="item.iconText"></span>
      <!-- 文字 -->
      <span>{{ item.text }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
      default: () => [],
      validator(val) {
        if (val.length >= 2 && val.length <= 5) {
          return true
        } else {
          return false
        }
      }
    }
  },

  data() {
    return {
      current: 0
    }
  },

  methods: {
    clickFn(val) {
      console.log(this.$parent);
      this.current = val;
      // this.$emit('change', this.list[val].componentName)
      this.$parent.comName=this.list[val].componentName
    }
  },
};
</script>

<style lang="less" scoped>
.my-tab-bar {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: white;

  .tab-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
  }
}

.current {
  color: #1d7bff;
}
</style>
