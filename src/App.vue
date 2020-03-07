<template>
  <div id="app">
    <el-container>
      <el-header>
        <NavMenu></NavMenu>
      </el-header>
      <el-main>
        <router-view></router-view> <!--路由出口 -->
      </el-main>
      <el-footer>Footer</el-footer>
    </el-container>
  </div>
</template>

<script>
import NavMenu from "./components/NavMenu";
export default {
  name: 'App',
  components: {NavMenu}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
