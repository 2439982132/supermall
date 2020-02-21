<template>
  <div class="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "TabBar"
  }
</script>

<style scoped>
  .tab-bar{
    /*横向显示*/
    display: flex;
    /*添加tab-bar的背景色*/
    background-color: #f6f6f6;
    /*把tab-bar调整为在底部显示*/
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;

    /*设置tab-bar与页面过度的阴影部分*/
    box-shadow: 0px -1px 1px rgba(100 100 100 .2);
  }
</style>