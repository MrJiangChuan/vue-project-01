<template>
  <div class='other'>
      <h1 v-on:click="myclick" v-bind:style="mystyle">{{msg}}</h1>
      <TimeSelector></TimeSelector>
      <input type="button" value="跳转到about页" @click="goabout" />
  </div>
</template>

<script>
  import TimeSelector from '@/components/TimeSelector.vue'
export default {
  name: 'Other',
  data() {
    return {
        msg: '这是我新添加的页面',
        mystyle: 'color: red'
    }
  },
  components: {
    TimeSelector
  },
  methods: {
    myclick() {
      // alert(123)
      this.mystyle='color: blue'
    },
    goabout() {
      this.$router.push({
        path: '/about',
        query: {
          name: 'Tom'
        }
      })
    }
  },
  //生命周期钩子函数
  beforeCreate() {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
    this.$axios.get('http://localhost:8080')
    .then(response => {
      console.log(response.data)
    })
    .catch(erro => {
      console.log('erro')
    })
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    console.log('mounted')
  },
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated: () => {
    console.log('updated')
  },
  // beforeRouteEnter: () => {
  //   console.log('beforeRouteEnter')
  // },
  // beforeRouteLeave: () => {
  //   console.log('beforeRouteLeave')
  // },
  // beforeRouteUpdate: () => {
  //   console.log('beforeRouteUpdate')
  // },
  beforeDestroy: () => {
    console.log('beforeDestroy')
  },
  destroyed: () => {
    console.log('destroyed')
  }
}
</script>

<style>
  .other {
    color: #42B983;
    border: #2C3E50 1px solid;
  }
</style>
