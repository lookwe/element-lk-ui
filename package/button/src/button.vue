<template>
    <button :class="['lk-buttom', getStyles()]" @click="onInalClick">
        <slot></slot>
    </button>
</template>
 
<script lang="ts">
import { Vue, Component, Prop, Emit } from "vue-property-decorator";

@Component
export default class LkBotton extends Vue {
    // 属性装饰
    @Prop({
        type: [Boolean, Number],
        default: false,
    })
    readonly long!: boolean | number;

    @Prop({
        type: [String, Number],
        default: "normal",
    })
    readonly size!: string | number;

    // 事件装饰
    @Emit("click")
    onInalClick(e: MouseEvent) {
        return e;
    }

    getStyles() {
        let sizeCss = {};
        if (typeof this.size === "string") {
            sizeCss = {
                "lk-btn-sxmall": this.size === "sxmall",
                "lk-btn-small": this.size === "small",
                "lk-btn-normal": this.size === "normal",
                "lk-btn-large": this.size === "large",
                "lk-btn-xlarge": this.size === "xlarge",
            };
        } else {
            sizeCss = {};
        }

        return {
            "lk-btn-long": this.long,
            ...sizeCss,
        };
    }
}
</script>
 
<style scoped lang="stylus">
Reize(mW, h, pLR, fs) {
    min-width: mW;
    height: h;
    padding: 0 pLR;
    font-size: fs;
}

.lk-buttom {
    Reize(64px, 36px, 16px, 0.875rem);
    border: 0 solid black;
    border-radius: 4px;
    color: #fff;
    background-color: #2d8cf0;
    font-weight: 500;
    // 每两个字符间隔
    letter-spacing: 0.09em;
    cursor: pointer;
    user-select: none;
    // 清除4周边轮廓颜色
    outline: none;
}

.lk-btn-long {
    width: 100%;
}

// 超小
.lk-btn-sxmall {
    Reize(36px, 20px, 9px, 0.625rem);
}

// 小
.lk-btn-small {
    Reize(50px, 28px, 12px, 0.75rem);
}

// 正常
.lk-btn-normal {
    Reize(64px, 36px, 16px, 0.875rem);
}

// 大
.lk-btn-large {
    Reize(78px, 44px, 19px, 0.875rem);
}

// 超大
.lk-btn-xlarge {
    Reize(92px, 52px, 23px, 1rem);
}
</style>