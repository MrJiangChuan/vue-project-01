<template>
  <div class="drawer">
    <el-button @click="drawer = true" type="primary" style="margin-left: 16px;">
      {{ mytitle }}
    </el-button>
    <el-drawer
      title="我是标题"
      :visible.sync="drawer"
      :direction="direction"
      :before-close="handleClose">
      <img src="../assets/head.jpg"/>
    </el-drawer>
  </div>
</template>

<script>
  export default {
    name: 'Drawer',
    props: {
      mytitle: String
    },
    data() {
          return {
            drawer: false,
            direction: 'ltr',
          }
    },
    methods: {
      handleClose(done) {
        done()
        // this.$confirm('确认关闭？')
        //   .then(_ => {
        //     done();
        //   })
        //   .catch(_ => {});
      }
    }
  }
</script>

<style>
</style>
