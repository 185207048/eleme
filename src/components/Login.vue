<template>
    <div class="login">
        <el-card class="box-card">
            <div class="main">
                <div class="close">X</div>
                <div class="title">开发者帐号登录</div>
                <div class="content">一个应用可以授权多个商家</div>
                <div class="main-ele-input">
                    <el-input class="ele-login" placeholder="开发者帐号"></el-input>
                    <el-input class="ele-login" placeholder="密码"></el-input>
                </div>
                <div class="my-option">
                    <div class="div1">忘记密码</div>
                    <div class="div2">手机验证码登录</div>
                </div>
                <div class="btn">
                    <el-button type="primary" class="btn-main">主要按钮</el-button>
                    <el-button class="btn-register">注册</el-button>
                </div>
                <div class="bottom">
                    <div class="bto-content">
                        <div>商家帐号登录</div>
                        <div>直接接入当前商家，无需授权</div>
                    </div>
                    <div class="bto-sign">></div>
                </div>
            </div>
        </el-card>
    </div>  
</template>
<script>
export default {
    name:'Login',
    data(){
        return{}
    }
}
</script>
<style>
  .text {
    font-size: 14px;
  }
  .box-card {
    width: 400px;
  }
  .main{
      width: 200px;
      height: 400px;
      text-align: center;
  }
  .main-ele-input{
      width:350px;
      margin:0 auto;
      text-align: center;
      margin: 5% 0 ;
  }
  .ele-login{
      margin:5% 0 ;
  }
  .close{
      position: absolute;
      right: 5%;
      color:#999;

  }
  .title{
      text-align: start;
      margin:2.5% 0;
      font-size: 24px;
  }
  .content{
      text-align: start;
      margin:2.5% 0;
      font-size: 14px;
      color:#999
  }
  .my-option .div1{
      float: left;
      color: #4fdde5;
  }
  .my-option .div2{
      right: 5%;
      position: absolute;
      color: #4fdde5;
  }
  .btn{
      margin-top:25%;
  }
  .btn-register{
      position: absolute;
      right: 5%;
      width: 150px;
  }
  .btn-main{
      position: absolute;
      left: 5%;
      width:150px;
  }
  .bottom{
      position: absolute;
      bottom:0;

  }
  .bto-content{
      float: left;
      text-align: start;
  }
  .bto-sign{
      position:absolute;
      right: -60%;
  }
</style>