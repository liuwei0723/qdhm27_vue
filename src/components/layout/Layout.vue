<template>
  <el-container>
    <el-aside width="auto">
      <div class="logo"></div>
      <el-menu
        router
        default-active="/layout/user"
        :collapse="isCollapse"
        :unique-opened="true"
        class="el-menu-vertical-demo"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
      >
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>用户管理</span>
          </template>

          <el-menu-item index="/layout/users">
            <i class="el-icon-menu"></i>用户列表
          </el-menu-item>

        </el-submenu>
        <el-submenu index="2">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>权限管理</span>
          </template>
          <el-menu-item index="/layout/roles">
            <i class="el-icon-menu"></i>角色列表
          </el-menu-item>
          <el-menu-item index="/layout/rights">
            <i class="el-icon-menu"></i>权限列表
          </el-menu-item>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>商品管理</span>
          </template>
          <el-menu-item index="/layout/goodslist">商品列表</el-menu-item>
          <el-menu-item index="3-2">商品分类</el-menu-item>
          <el-menu-item index="3-3">商品参数</el-menu-item>
        </el-submenu>
      </el-menu>
    </el-aside>
    <el-container>
      <el-header>
        <!-- 字体图标 -->
        <i @click="toggleMenu" style="font-size:30px;color:orange;" class="iconfont icon-webicon03"></i>
        <div class="stitle">电商后台管理系统</div>
        <a href="javascript:;" @click="logout" class="logoutbtn">退出</a>
      </el-header>
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </el-container>
</template>

<style scoped>
.btnsize {
  font-size: 36px;
  color: #989898;
  cursor: pointer;
  line-height: 60px;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.el-container {
  height: 100%;
}
.el-header,
.el-footer {
  background-color: #b3c0d1;
  color: #333;
  text-align: left;
  line-height: 60px;
}
.el-aside {
  background-color: #545c64;
  color: #333;
  text-align: left;
  display: block;
}
.el-menu {
  border-right: 0
}
.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: left;
  overflow: '';
}
.logoutbtn {
  position: absolute;
  right: 10px;
  color: orange;
}
.el-header {
  background-color: #545c64;
}
.logo {
  height: 60px;
  background: url(../../assets/logo.png);
  background-size: cover;
  background-color: #989898;
}
.stitle {
  position: absolute;
  font-size: 28px;
  overflow: hidden;
  width: 300px;
  color: #fff;
  left: 600px;
  top: 0px;
}
</style>

<script>
export default {
  data() {
    return {
      isCollapse: false
    }
  },
  methods: {
    toggleMenu() {
      this.isCollapse = !this.isCollapse
    },
    logout() {}
  }
}
</script>