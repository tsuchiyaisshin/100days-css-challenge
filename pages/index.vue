<template>
  <div>
    <el-main>
      <el-row class="tac">
        <el-container>
          <challenge-card
            :cardName="challengeName"
          >
            <component :is="challengeComponent"></component>
          </challenge-card>
        </el-container>
      </el-row>
    </el-main>
    <el-footer>
      <el-pagination
        @current-change="changeChallengeCard"
        :current-page.sync="challengeNumber"
        layout="prev, pager, next"
        :total="1000">
      </el-pagination>
    </el-footer>
  </div>
</template>

<script lang="ts">
import { Component } from "nuxt-property-decorator"
import Vue from "vue"
import challenges from "@/assets/challenges.json"
import ChallengeCard from "@/components/atoms/ChallengeCard.vue"
import Day1 from "@/components/challenges/Day1.vue"

@Component({
  components: {
    ChallengeCard,
    Day1
  }
})
export default class Default extends Vue {
  challenges = challenges
  challengeNumber = 1
  challengeName = 'Card Name'
  challengeComponent = 'Day1'
  changeChallengeCard(val: number) {
    const target = this.challenges.find(challnge => challnge.id === val)
    if (target) {
      this.challengeNumber = target.id
      this.challengeName = target.name
      this.challengeComponent = target.component
    }
  }
}
</script>
