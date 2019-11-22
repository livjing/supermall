<template>
    <div id="tab-bar">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'TarBar'
    }
</script>

<style>

    #tab-bar {

        /* 等分 */
        display: flex;

        /* 背景色 灰白色 */
        background-color: #f6f6f6;

        /* 沉底 */
        position: fixed;
        /* 左 右 底 边框0 */
        left: 0;
        right: 0;
        bottom: 0;

        /* tabbar 与 主内容展示区的连接处 加上阴影 显示更加平滑 */
        /* x往右正 y往下正 透明度 */
        box-shadow: 0px -3px 10px rgba(100, 100, 100, 0.3);
    }



</style>
