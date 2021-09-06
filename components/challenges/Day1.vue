<template>
    <div class="frame">
        <div class="center">
            <div class="menu-icon" :class="isAnimation ? '' : 'active'" @click="changeAnimation()">
                <div class="line-1"></div>
                <div class="line-2"></div>
                <div class="line-3"></div>
            </div>
        </div>
    </div>
</template>

<script>
import Vue from "vue"
import { Component } from "vue-property-decorator"

@Component
export default class Day1 extends Vue {
    isAnimation = true
    changeAnimation() {
        if (this.isAnimation) {
            this.isAnimation = false
        } else {
            this.isAnimation = true
        }
    }

    get isAnimationValue() {
        return this.isAnimation
    }
}
</script>

<style lang="scss" scoped>
.frame {
    width: 400px;
    height: 400px;
    border-radius: 2px;
    box-shadow: 1px 2px 10px 0px rgba(0,0,0,0.3);
    background: #3FAF82;
    color: #fff;
}

.center {
    position: relative;
    top: 45%;
    left: 40%;
}


$menu-icon-line-height: 8px;
$menu-icon-line-space: 14px;
$menu-icon-line-offsetY: $menu-icon-line-height + $menu-icon-line-space;
$menu-icon-height: (3*$menu-icon-line-height) + (2*$menu-icon-line-space);
$cubic-bezier-in: cubic-bezier(0.30,1,0.70,1);
$cubic-bezier-out: cubic-bezier(1,0.70,1,0.30);

.menu-icon {
    width: 80px;
    height: $menu-icon-height;
    cursor: pointer;
    z-index: 50;

    .line-1,
    .line-2,
    .line-3 {
        height: $menu-icon-line-height;
        width: 100%;
        background-color: #fff;
        border-radius: 3px;
        box-shadow: 0 2px 10px 0 rgba(0,0,0,0.3);
        transition: background-color .2s ease-in-out;
    }
    .line-1 {
        animation: animate-line-1-rev .7s ease-in-out;
    }
    .line-2 {
        margin: $menu-icon-line-space 0;
        animation: animate-line-2-rev .7s ease-in-out;
    }
    .line-3 {
        animation: animate-line-3-rev .7s ease-in-out;
    }

    &:hover {
        .line-1,
        .line-2,
        .line-3 {
            background-color: #fff;
        }
    }

    &.active {

        .line-1,
        .line-2,
        .line-3 {
            background-color: #fff;
        }


        .line-1 {
            animation: animate-line-1 .7s $cubic-bezier-in forwards;
        }
        .line-2 {
            animation: animate-line-2 .7s $cubic-bezier-in forwards;
        }
        .line-3 {
            animation: animate-line-3 .7s $cubic-bezier-in forwards;
        }
    }
}

@keyframes animate-line-1 {
    0% {
        transform: translate3d(0, 0, 0) rotate(0deg);
    }
    50% {
        transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(0);
    }

    100% {
        transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(45deg);
    }
}
@keyframes animate-line-2 {
    0% {
        transform: scale(1);
        opacity: 1;
    }
    100% {
        transform: scale(0);
        opacity: 0;
    }
}
@keyframes animate-line-3 {
    0% {
        transform: translate3d(0, 0, 0) rotate(0deg);
    }
    50% {
        transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(0);
    }

    100% {
        transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(135deg);
    }
}
@keyframes animate-line-1-rev {
    0% {
        transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(45deg);
    }
    50% {
        transform: translate3d(0, $menu-icon-line-offsetY, 0) rotate(0);
    }

    100% {
        transform: translate3d(0, 0, 0) rotate(0deg);
    }
}
@keyframes animate-line-2-rev {
    0% {
        transform: scale(0);
        opacity: 0;
    }
    100% {
        transform: scale(1);
        opacity: 1;
    }
}
@keyframes animate-line-3-rev {
    0% {
        transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(135deg);
    }
    50% {
        transform: translate3d(0, -$menu-icon-line-offsetY, 0) rotate(0);
    }

    100% {
        transform: translate3d(0, 0, 0) rotate(0deg);
    }
}
</style>