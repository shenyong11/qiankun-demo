<template>
  <div id="qiankun-main-app">
    <el-container style="height: 500px; border: 1px solid #eee">
      <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
        <el-menu>
          <el-submenu index="1">
            <template slot="title">子应用1</template>
            <el-menu-item v-for="menu in menus" :key="menu.key" @click="gotoPath(menu.path)">{{menu.title}}</el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
      
      <el-container>
        <router-view></router-view>
        <div id="frame"></div>
      </el-container>
    </el-container>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      menus: [
        {
          key: "Home",
          title: "主页",
          path: "/"
        },
        {
          key: "VueMicroApp",
          title: "Vue 主页",
          path: "/vue"
        },
        {
          key: "VueMicroAppList",
          title: "Vue 列表页",
          path: "/vue/list"
        }
      ]
    }
  },
  methods: {
    gotoPath(path) {
      this.$router.push({ path })
    }
  }
}
</script>

<style>
</style>
