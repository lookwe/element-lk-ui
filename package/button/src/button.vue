<template>
    <button class="lk-buttom" @click="onInalClick">
        <slot></slot>
    </button>
</template>
 
<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class LkBotton extends Vue {
    onInalClick() {
        this.$emit("click");
    }
}
</script>
 
<style scoped lang="stylus">
.lk-buttom {
    min-width: 64px;
    height: 36px;
    padding: 0 16px;
    border: 0 solid black;
    border-radius: 4px;
    color: #fff;
    background-color: #2d8cf0;
    font-size: 0.875rem;
    font-weight: 500;
    // 每两个字符间隔
    letter-spacing: 0.09em;
    cursor: pointer;
    user-select: none;
    // 清除4周边轮廓颜色
    outline: none;
}
</style>