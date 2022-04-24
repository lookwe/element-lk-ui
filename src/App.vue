<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <lkButtom @click="onButClick" long>点击提交</lkButtom>
    </div>
</template>

<script lang="ts">
// Vue属性装饰器
import { Component, Vue } from "vue-property-decorator";
import lkButtom from "../package/button/src/button.vue";

@Component({
    components: {
        lkButtom,
    },
})
export default class App extends Vue {
    onButClick(e: MouseEvent) {
        console.log(e);
    }
}
</script>

<style lang="stylus">
html, body {
    box-sizing: border-box;
    font-size: 18px;
    font-family: 'Arial', 'Helvetica', 'sans-serif';
}

*, ::before, ::after {
    box-sizing: inherit;
    font-size: inherit;
    font-family: inherit;
}
</style>
