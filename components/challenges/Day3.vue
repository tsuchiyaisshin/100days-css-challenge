<template>
    <div class="frame">
        <div class="center">
            <div class="dot-1"></div>
            <div class="dot-2"></div>
            <div class="dot-3"></div>
        </div>
    </div>
</template>

<script>
import Vue from "vue"
import { Component } from "vue-property-decorator"

@Component
export default class Day3 extends Vue {}
</script>

<style lang="scss" scoped>
.frame {
    width: 400px;
    height: 400px;
    border-radius: 2px;
    box-shadow: 1px 2px 10px 0px rgba(0,0,0,0.3);
    background: #E56262;
    color: #fff;
}

.center {
    position: relative;
    left: 22%;
    top: 22%;
}

$bezier: cubic-bezier(.21,.98,.6,.99);

.dot-1 {
    position: absolute;
    z-index: 10;
    width: 30px;
    height: 30px;
    top: 95px;
    left: 95px;
    background: #fff;
    border-radius: 50%;
    animation-fill-mode: both;
    animation: jump-jump-1 2s $bezier infinite alternate;
}

.dot-2 {
    position: absolute;
    z-index: 9;
    width: 60px;
    height: 60px;
    top: 80px;
    left: 80px;
    background: #fff;
    border-radius: 50%;
    animation-fill-mode: both;
    animation: jump-jump-2 2s $bezier infinite alternate;
}

.dot-3 {
    position: absolute;
    z-index: 8;
    width: 90px;
    height: 90px;
    top: 65px;
    left: 65px;
    background: #fff;
    border-radius: 50%;
    animation-fill-mode: both;
    animation: jump-jump-3 2s $bezier infinite alternate;
}

@keyframes jump-jump-1 {
    0%, 70% {
        box-shadow: 2px 2px 3px 2px rgba(0,0,0,0.2);
        transform: scale(0);
    }

    100% {
        box-shadow: 10px 10px 15px 0 rgba(0,0,0,0.3);
        transform: scale(1);
    }
}

@keyframes jump-jump-2 {
    0%, 40% {
        box-shadow: 2px 2px 3px 2px rgba(0,0,0,0.2);
        transform: scale(0);
    }

    100% {
        box-shadow: 10px 10px 15px 0 rgba(0,0,0,0.3);
        transform: scale(1);
    }
}

@keyframes jump-jump-3 {
    0%, 10% {
        box-shadow: 2px 2px 3px 2px rgba(0,0,0,0.2);
        transform: scale(0);
    }

    100% {
        box-shadow: 10px 10px 15px 0 rgba(0,0,0,0.3);
        transform: scale(1);
    }
}
</style>