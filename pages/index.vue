<template>
  <div>
    <el-main>
      <el-row class="tac">
        <el-container>
          <el-col :span="6">
            <!-- ここにcss -->
            <el-card></el-card>
          </el-col>
        </el-container>
        <div class="block">
          <span class="demonstration">Jump to</span>
          <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page.sync="currentPage3"
            :page-size="100"
            layout="prev, pager, next, jumper"
            :total="1000">
          </el-pagination>
        </div>
      </el-row>
    </el-main>
  </div>
</template>

<script lang="ts">
import { Component } from "nuxt-property-decorator"
import Vue from "vue"

@Component
export default class Default extends Vue {
}
</script>
