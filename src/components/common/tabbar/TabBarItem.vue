<template>
    <div class="tab-bar-item" @click="itemClick">
      <div v-if="!isActive"><slot name="item-icon"></slot></div>
      <div v-else><slot name="item-icon-active"></slot></div>
      <div :style="activeStyle"><slot name="item-text"></slot></div>
    </div>
</template>

<script>
  export default {
    name: "TabBarItem",
    props: {
      path: String,
      activeColor: {
        type: String,
        default: 'red'
      }
    },
    data(){
      return{
        /*isActive: false*/
      }
    },
    computed:{
      isActive() {
        return this.$route.path.indexOf(this.path) !== -1;
      },
      activeStyle() {
        return this.isActive ? {color: this.activeColor} : {}
      }
    },
    methods: {
      itemClick() {
         this.$router.push(this.path)
      }
    }
  }
</script>

<style scoped>
  .tab-bar-item{
    /*flex属性可以使tab-bar-item均等分*/
    flex: 1;
    /*设置tab-bar-item居中显示*/
    text-align: center;
    /*设置tab-bar的高度*/
    height: 49px;
    /*设置字体的大小*/
    font-size: 14px;
    /*设置图片的内边距*/
    margin-top: 3px;

  }
  .tab-bar-item img {
    /*设置图片的大小*/
    height: 24px;
    /*取消图片与字体的间隔*/
    vertical-align: middle;
    /*设置图片与文字的间隔*/
    margin-top: 2px;
  }
</style>