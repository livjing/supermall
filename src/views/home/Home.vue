<template>
  <div id="home">
    <!--  指定替换中间的slot  -->
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <h2>首页</h2>

  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";

  export default {
    name: "Home",
    components: {
      NavBar
    }
  }
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #ffffff;
  }
</style>
