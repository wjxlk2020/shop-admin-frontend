<template>
<div class="admin-container">
  <el-container>
      <!-- 左侧菜单栏 -->
      <el-aside width="auto">
          <!-- 预留存放logo的位置 -->
          <div class="logo"></div>

          <!-- 菜单栏 -->
          <app-aside :isCollapse="isCollapse"></app-aside>
      </el-aside>

      <!-- 右侧内容区域 -->
      <el-container>
          <!-- 头部 -->
          <el-header>
            <app-header @onChange="changeCollapse"></app-header>
          </el-header>
          <!-- 主体 -->
          <el-main>
            <router-view></router-view>
          </el-main>
      </el-container>
  </el-container>
</div>

</template>

<script>

//引入组件
import Aside from "../components/Aside"
import Header from "../components/Header"
// import BreadCrumb from "../components/BreadCrumb"



export default {
  name:"admin-index",
  data(){
    return {
      //控制菜单栏的展开
       isCollapse: false,
    }
  },
  //注册组件，注意组件名称不要和html的标签名重复
  components: {
    "app-aside": Aside,
    "app-header":Header,
    // "app-breadcrumbs":BreadCrumb
  },

  methods:{
    //修改菜单栏的收起展开
    changeCollapse(){
      this.isCollapse=!this.isCollapse;
    }
  }
}
</script>

<style>
/* container外层的div */
.admin-container{
    position: fixed;
    width:100%;
    top:0;
    bottom:0;
}

.el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
      display: flex;
      flex-direction: column;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  .el-container {
    margin-bottom: 40px;
    /*继承admin-container的高度*/
    height: 100%;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }

  .logo{
      height:60px;
      background:#454f5a;
  }
</style>
