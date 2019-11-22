<template>
    <!--  在组件内部监听点击事件  -->
    <div class="tab-bar-item" @click="itemClick">
        <!-- 问题: 所有的item都展示同一样的图片和文本 -->
        <!-- <img src="../../assets/img/tabbar/home.svg" alt=""> -->
        <!-- <div>首页</div> -->

        <!-- 担心插槽替换的问题,所有插槽都外包个div,将判断或样式都放置在外包装上做 -->
        <div v-if="isActive">
            <!-- 再添加一个slot用以显示active图片-->
            <slot name="item-icon-active"></slot>
        </div>
        <div v-else>
            <!-- 解决: 使用slot可以动态替换  -->
            <slot name="item-icon"></slot>
        </div>

        <!-- 添加文选定的颜色 -->
        <!-- <div :class="{active: isActive}">-->
        <div :style="activeStyle">
            <!-- <slot :class="{active: isActive}" name="item-text"></slot>-->
            <!--
            直接在slot中改变字体颜色,最终被替换,所以导致字体颜色失效
            所以不直接在slot内修改字体样式,而是外套个div来使用
            -->
            <slot name="item-text"></slot>
        </div>

    </div>
</template>

<script>
    export default {
        name: "TabBarItem",
        // 添加属性path,用于跳转
        props: {
            path: String,
            activeColor: {
                type: String,
                default: 'red'
            }
        },
        data() {
            return {
                // isActive: false
            }
        },
        computed: {
            isActive() {
                return this.$route.path.indexOf(this.path) !== -1;
            },
            activeStyle() {
                return this.isActive ? {color: this.activeColor} : {}
            }
        },
        methods: {
            itemClick() {
                console.log('itemClick');
                // 点击实现跳转
                if (this.$route.path != this.path) {
                    this.$router.replace(this.path);
                }
            }
        }
    }
</script>

<style scoped>
    .tab-bar-item {

        /* 均等分 */
        flex: 1;

        /* 每个居中 */
        text-align: center;

        /* 高度 */
        height: 49px;

        /* 调整文字 */
        font-size: 14px;
        /* 字体加粗 */
        font-weight: bold;

    }

    .tab-bar-item img {
        /* 调整图片大小 */
        width: 24px;
        height: 24px;

        /*  调整图片上层间距  */
        margin-top: 3px;

        /*  图片下面会多3个像素  */
        vertical-align: middle;
    }

    /*使用:style, 已经不需要了*/
    /*.active {*/
    /*    color: red;*/
    /*}*/
</style>
