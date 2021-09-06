<template>
  <div>
      <el-card class="box-card">
        <div slot="header" class="clearfix">
            <span>{{ cardName }}</span>
        </div>
        <slot></slot>
      </el-card>
  </div>
</template>

<script lang="ts">
import Vue from "vue"
import { Component, Prop } from "vue-property-decorator"
import Day1 from "@/components/challenges/Day1.vue"

@Component({
    components: {
        Day1
    }
})
export default class ChallengeCard extends Vue {
    @Prop({ type: String, default: 'Card Name' })
    cardName!: string 
}
</script>
