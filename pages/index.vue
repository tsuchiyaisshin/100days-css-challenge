<template>
  <div>
    <el-main>
      <el-row class="tac">
        <el-container>
          <challenge-card
            :cardName="challengeName"
            :challengeNumber="challengeNumber"
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
import Sorry from "@/components/challenges/Sorry.vue"

@Component({
  components: {
    ChallengeCard,
    Sorry,
  }
})
export default class Default extends Vue {
  challenges = challenges
  challengeNumber = 1
  challengeName = 'Hunbuger Menu'
  challengeComponent = 'Day1'
  changeChallengeCard(val: number) {
    const target = this.challenges.find(challnge => challnge.id === val)
    if (target) {
      this.challengeNumber = target.id
      this.challengeName = target.name
      this.challengeComponent = target.component
    } else {
      this.challengeNumber = val
      this.challengeName = 'In development...'
      this.challengeComponent = 'Sorry'
    }
  }
}
</script>
