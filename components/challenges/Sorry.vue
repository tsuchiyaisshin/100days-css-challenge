<template>
    <div class="frame">
        <div class="soon_text">comming soon...</div>
    </div>
</template>

<script>
import Vue from "vue"
import { Component } from "vue-property-decorator"

@Component
export default class Sorry extends Vue {}
</script>

<style lang="scss" scoped>
.frame {
    width: 400px;
    height: 400px;
    display: table-cell;
    vertical-align: middle;
}
.soon_text {
    text-align: center;
    color: rgb(0, 0, 0, 0.12);
}
</style>