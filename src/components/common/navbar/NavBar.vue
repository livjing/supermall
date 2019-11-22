<template>
  <div class="nav-bar">
    <div class="left">
      <slot name="left"></slot>
    </div>
    <div class="center">
      <slot name="center"></slot>
    </div>
    <div class="right">
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "NavBar"
  }
</script>

<style scoped>
  .nav-bar {
    /* 等分 */
    display: flex;

    /* 高度,直接设置line-height,可以文字上下居中 */
    /* 如果不设置文字和高度,它不会显示,应该变成0了*/
    height: 44px;
    line-height: 44px;

    /* 让文本居中 */
    text-align: center;

    /*添加阴影线效果*/
    box-shadow: 0 1px 1px rgba(100, 100, 100, 0.1);
  }

  .left, .right {
    /*左右各占60px*/
    width: 60px;

    /*测试用*/
    /*background-color: red;*/
  }

  .center {
    /*中间占用剩余所有*/
    flex: 1;

    /*测试用*/
    /*background-color: blue;*/
  }

</style>
