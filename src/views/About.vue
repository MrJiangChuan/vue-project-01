<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h3>{{msg}}</h3>
    <h3>{{$route.query.name}}</h3>
    <input type="text" v-model="msg" />
    <Drawer mytitle="弹出菜单栏" />
  </div>
</template>

<script>
  import Drawer from '@/components/Drawer.vue'
  export default {
    name: 'About',
    data() {
      return {
        msg: "other"
      }
    },
    components: {
      Drawer
    }
  }
</script>
