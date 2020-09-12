<template>
  <div class="timeSelector">
    <el-time-select
      v-model="value"
      :picker-options="{
        start: '08:30',
        step: '00:15',
        end: '18:30'
      }"
      placeholder="选择时间">
    </el-time-select>
  </div>
</template>

<script>
    export default {
      name: 'TimeSelector',
      data() {
        return {
          value: ''
        }
      }
    }
</script>

<style>
</style>
