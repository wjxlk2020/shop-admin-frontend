<template>
  <div id="app">
    <div class="login">
      <h4>登录</h4>
      <!-- 账号 -->
      <div class="login_id">
        <span>账号</span>
        <el-input class="input_id" placeholder="请输入内容" v-model="goods.user" clearable> </el-input>
      </div>
      <!-- 密码 -->
      <div class="login_pwd">
        <span>密码</span>
        <el-input class="input_pwd" placeholder="请输入密码" v-model="goods.password" show-password></el-input>
      </div>
        <div class="btn">
          <el-button class="btn_sbt" type="primary submit" @click="submitClick">提交</el-button>
          <el-button class="btn_reset" type="reset" @click="handleClick">重置</el-button>
        </div>
    </div>
  </div>
</template>

<script>


// //导入axios
// import axios from "axios"

export default {
  name: 'app',
  
  // data() {
  //     return {
  //       input10: '',
  //       input11: ''
  //     }
  //   },
  data(){
    return {
      goods:{
        user:"",
        password:""
      }
    }
  },
  // mounted () {
  //   //调用axios的get请求
  //   this.$axios.get("https://api.github.com/users").then(res=>{
  //     console.log(res)
  //   })
  // }
  methods:{
    //点击重置清空
    handleClick:function(){
    this.goods=''
      // this.input10='',
      // this.input11=''
    },
    //获取账户和密码
    submitClick:function(){
      // let inputId =this.input10;
      // let inputPwd = this.input11
      // alert(inputId+inputPwd)
      
      // 获取数据
      console.log(this.goods);
      
    }
  },
 
 
}
</script>

<style lang="less">
  #app{
    .login{
      width: 50%;
      // height: 300px;
      margin: 300px auto;
      h4{
        color:skyblue;
        text-align: center;
      }
      // border: 1px solid #000;
       .login_id{
         margin-left: 30%;
         margin-bottom: 20px;
         span{
           margin-right: 10px;
         }
         .input_id{
           width: 300px;
         }
       }
       .login_pwd{
         margin-left: 30%;
         span{
           margin-right: 10px;
         }
         .input_pwd{
           width: 300px;
         }
       }
      //  按钮
      .btn{
        padding: 10px 0;
        text-align: center;
        margin: 0 10px;
        .btn_sbt{
          margin-right: 10px;
        }
      }
    }
  }

</style>
