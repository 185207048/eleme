<template>
    <div class="header-bar">
                <span class="header-title">
                    <span><img class="header-img" :src="require('../assets/image/logo.png')" /></span>
                    <span class="header-point">·</span>
                    <span class="header-play">商家开发平台</span>
                </span>
                <span class="header-mylist">
                    <ul class="header-list">
                        <li class="">首页</li>
                        <li>文档中心</li>
                        <li>管理中心</li>
                        <li>帮助中心</li>
                        <li>
                            <el-input
                                placeholder="搜索"
                                prefix-icon="el-icon-search"
                                class="header-search"
                                >
                            </el-input>
                        </li>
                        <li>|</li>
                        <li @click="dialogVisible = true">登录</li>
                        <li>
                            <div class="header-register" @click="register">注册</div>
                        </li>
                    </ul>
                </span>

        <el-dialog
                style="height: 1000px"
                :modal-append-to-body="false"
                title="开发者账号登录"
                :visible.sync="dialogVisible"
                width="480px"
                :before-close="handleClose"
        >
            <div  style="    color: #8492a6;
        text-align: left;
        margin-top: -24px;">一个应用可以授权多个商家</div>
            <el-input style="margin-top: 24px;"  v-model="username" placeholder="开发者账号"></el-input>
            <el-input style="margin-top: 24px;" type="password" v-model="password" placeholder="密码"></el-input>
            <div style="  display: flex;
        align-items: center;
        justify-content: space-between;
        margin-top: 12px;">
                    <span style=" color: #20a0ff;
        cursor: pointer;
        padding-bottom: 6px;">忘记密码</span>
                <span style=" color: #20a0ff;
        cursor: pointer;
        padding-bottom: 6px;">手机验证码登陆</span>
            </div>
            <div style="  display: flex;
        align-items: center;
        justify-content: center;
        margin-top: 12px; ">
                <el-button style="width: 170px" type="primary" @click="login">登录</el-button>
                <el-button style="width: 170px" @click="register">注册</el-button>
            </div>
            <el-divider></el-divider>
            <div style="  display: flex;
        align-items: center;
        justify-content: space-between;
        margin-top: 12px;">
                <div style="display: flex;
        flex-direction: column;
        color: #8492a6;">
                    <span style="color:#1f2d3d">商家账号登陆</span>
                    <span style=" color: #20a0ff;
        cursor: pointer;
        padding-bottom: 6px;">直接接入当前商家，无需授权</span>
                </div>
                <div>></div>
            </div>
        </el-dialog>



            </div>
</template>
<script>

export default {
    name:'header',
    data(){
        return{
            login_hidden:false,
            dialogVisible: false,
            username: "",
            password: ""
        }
    },
    methods:{
        login(){
            if (this.username && this.password) {
                if (/^1[3456789]\d{9}$/.test(this.username)) {
                    this.$message("登录成功!");
                    this.dialogVisible = false;
                } else {
                    this.$message("手机号格式不正确!");
                }
            } else {
                this.$message("有空项!");
            }
        },
        register(){
            this.login_hidden = !this.login_hidden
        }
    }
}
</script>
<style scoped>
*{
    list-style: none;
}
.my-login{
    position: absolute;
    left: 40%;
    top:100%;
}
.el-header{
    padding: 0;
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  body > .el-container {
    margin-bottom: 40px;
  }
   .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
     background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
     background-color: #d3dce6;
  }
  .header-back1{
      width: 100%;
      height: 550px;
      background-image: url("../assets/image/back1.jpg");
      background-size: 100% 100%;
  }
  .header-back2{
      width: 100%;
      height: 550px;
      background-image: url("../assets/image/back2.jpg");
      background-size: 100% 100%;
  }
  .header-bar{
      width: 100%;
      height: 60px;
      float: left;
      padding:20px 0;
      position: absolute;
      z-index: 999;
  }
  .header-title{
      margin:0 auto;
  }
  .header-img{
      margin-left:10%;
      width: 70px;
      cursor: pointer;
  }
  .header-point{
      margin:0 0.5%;
      color:white;
      font-size: 25px;

  }
  .header-play{
      color:white;
      position: relative;
      top:-5px;
      cursor: pointer;
  }
  .header-list{
      position: relative;
      color:white;
      list-style-type: none;
      display: flex;
      align-self: center;
      align-items:center;

  }
  .header-list li{
      margin:0.5% 2.5%;
      cursor: pointer;

  }
  .header-search{
      width: 160px;
      opacity:0.6;
  }
  .header-mylist{
      margin-right: 10%;
      width: 850px;
      float: right;
  }
  .header-register{
      width: 70px;
      height: 30px;
      text-align: center;
      line-height: 30px;
      border: 1px solid white;
      border-radius: 30px ;
  }

  .header-carousel{
      height: 550px;
      width: 100%;
  }
  .tini-box{
       width: 100%;
      height: 100px;
      background-image: url("../assets/image/back2.jpg");
      background-size: 100% 100%;
  }

</style>
