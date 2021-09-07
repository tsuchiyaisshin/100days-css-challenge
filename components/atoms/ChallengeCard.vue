<template>
  <div>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
            <span class="no">Day.{{ challengeNumber }}</span>
            <span class="name">{{ cardName }}</span>
        </div>
        <slot></slot>
      </el-card>
  </div>
</template>

<script lang="ts">
import Vue from "vue"
import { Component, Prop } from "vue-property-decorator"

@Component
export default class ChallengeCard extends Vue {
    @Prop({ type: String, default: 'Card Name' })
    cardName!: string 

    @Prop({ type: Number,  default: 1 })
    challengeNumber!: number
}
</script>
<style lang="scss" scoped>
.no {
    font-weight: bold;
}
.name {
    margin-left: 16px;
    text-align: center;
}
</style>
