<template>
   <div class="main">
        <Header />
        <div class="tini-box"></div>
        <div>
            <div class="header-carousel">
                <el-carousel trigger="click" indicator-position="none" arrow="never" :autoplay="false" ref="carousel">
                    <el-carousel-item >
                        <div class="header-back1">
                            <div class="header-title">
                                <div class="header-title-1">饿了么开放平台，连接千万商家</div>
                                <div class="header-title-2">与 3,000+ 位开发者一起，共建 O2O 行业良性生态</div>
                                <el-button type="primary" round class="btn-add1">立即免费加入</el-button>
                            </div>
                            
                        </div>
                    </el-carousel-item>
                    <el-carousel-item>
                        <div class="header-back2">
                            <div class="header-title">
                                <div class="header-title-1">饿了么开放平台，连接千万商家</div>
                                <div class="header-title-2">与 3,000+ 位开发者一起，共建 O2O 行业良性生态</div>
                                <el-button type="primary" round class="btn-add2">立即免费加入</el-button>
                            </div>
                        </div>
                    </el-carousel-item>
                </el-carousel>
                <div class="point-contorl">
                    <div class="point1 point-white" @click="clickpoint"></div>
                    <div class="point2" @click="clickpoint"></div>
                </div>
            </div>
            <div class="adv">
                <ul>
                    <li>
                        <span class="adv-new">
                            <span class="adv-new-fitin">
                                NEW 
                            </span>
                        </span>
                        <span class="adv-content">关于服务市场转账手续费变更公告</span>
                    </li>
                     <li>
                        <span class="adv-new">
                            <span class="adv-new-fitin">
                                NEW
                            </span>
                        </span>
                        <span class="adv-content">【接口变更】订单接口变更</span>
                    </li>
                      <li>
                        <span class="adv-all">全部公告 ></span>
                    </li>
                </ul>
                    
            </div>
        </div>
        <div class="ele-body">
            <div class="ele-body-title">资源优势和接入流程</div>
            <span class="ele-body-move"></span>
            <div class="ele-body-choose">
                <span class="ele-body-title-1" @click="moveWhite">平台服务商</span>
                <span class="ele-body-title-2" @click="moveWhite">提供经营管理增值服务</span>
                <span class="ele-body-fitin">xxxxxx</span>
                <span class="ele-body-title-1" @click="moveWhite">企业服务商</span>
                <span class="ele-body-title-2" @click="moveWhite">提供订单商品基础服务</span>
            </div>
            <div class="ele-sign">
            <div v-if="type_hidden">
                <div class="ele-sign-font">
                    <span class="ele-sign-block font-black" @click="changetitle">资源优势</span>
                    <span class="ele-sigin-point">·</span>
                    <span class="ele-sign-block" @click="changetitle">接入流程</span>
                </div>
                <div class="ele-sign-type" v-if="title_hidden">
                    <div class="card-first">
                         <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHgAAAB4CAYAAAA5ZDbSAAAACXBIWXMAABYlAAAWJQFJUiTwAAADg0lEQVR42u3cy00bURiG4Q8ra0MJ3nlpSy7AlOC9kTLpgA48dEAHTCSzpwRcAJJnyc50ENOAs+AoiogiZsbnft5Xyo4kBz+aGc/tvzidTqJ8G/ERAEwAE8AEMAFMABPAABPABDABTAATwAQwwJRl3/gIhvfyqitJc/NHkvaS9oupfsWyxgue6BgEO5FUS/r+nx/5KaleTHUAOD3cStK9pMsvfvQo6XYxVZMl8N2jKkmVpKXj32Enqdms3X+QBveh51/7ERLZOvDdoyaSniTNPP8uraTVZu1mtzgQNziyVWCDu++w+3LVUdLcNvKZuEGRbZ8mPQXElfm/nyLElaQH82+lCWyOuTOFb2bWEhNuMGSbW3CleKoixA2CbBN4GRHwMlJc78hcqvSP6xUZ4DC43pABDofrBRngsLjOkUfgBsd1ijwCNwpcZ8gjcKPLKvKoUNxVpLh/I68AHoY7kcLeo+1YY9YKcM9qhb0h0rVLs1aAe7Yqaa1FAb+8ap7I1vtnKzZrBrhjV6WtmStZmVca8KG0NRcFbJ5TfktoyW/nPltd4i66KWmtxQEvpqr18Yht7LVmrQAPqNLHI7axdpSlZ9yKBF5MtZd0HSnyUdK1WSPAmSFbxS3+PDgyZOu4xQNHhOwE1zbwLiK3XULIznBtA8d0ftkksiU7xZXsv124V/j3k9rNevgdGHP35lnu7zo5x3VxDF5FcCw76x6qpy3ZC651YPNe7lxhrhS1svRusGNkb7jWd9GfdteVEh/h4GB37RXXKXAuWUT2jst5sL/ddRBcgP0gB8MF2D1yUFyAhyF3PUtoJc1D4vIl67wvX5WkW/17YaeVdB96wh3AdrEnZgs/xLY2gDOPYzDAlHLOBoLf1O+VPF6q3NZjK19qcpuSa/0YfFO/TxRw2uy2Hh8GwgZdt6spuVaBDW7wabN9kXOdkuviGJzqtNnspuRaBzbH3CimzZq19DnmZjUl19UWXCmeqgLW7R041Wmz2UzJ5Ty4wAAGmAAmgAlgApgAJoABJoAJYAKYACaACWCACWACmAAmgAlgAphsA6c6bTbZKbm+gZuIPqimgHV3yvbbhVFMm93W417TZnOYkuvrGJzqtNnkp+R6ATbv5QadNjvkBfBcpuQ630V/2l1XYoTDl+tOboQDcR5MABPABDABDDABTAATwAQwAUwAA0wAE8AEMAFMZ/Ybhrp2girPRfkAAAAASUVORK5CYII=" alt="">
                         <div class="font1">服务市场</div>
                         <div class="font2">打造专业服务市场，与商家端后台无缝对接，全平台分发您的应用</div>
                    </div>
                    <div class="card-second">
                         <img src="data:image/png;base64,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" alt="">
                         <div class="font1">海量活跃商家</div>
                         <div class="font2">共享饿了么百万活跃商家资源，在线订购您的应用服务</div>
                    </div>
                     <div class="card-third">
                         <img src="data:image/png;base64,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" alt="">
                         <div class="font1">丰富的 IT 工具</div>
                         <div class="font2">提供丰富的 API 接口，除饿了么商家的核心订单功能外，提供更多专属接口</div>
                    </div>
                </div>
                <div v-if="!title_hidden">
                    <ul class="ele-list">
                        <li>
                            <div>
                                <div class="number">1</div>
                                <div class="title">商务接洽</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">2</div>
                                <div class="title">成为平台服务商</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">3</div>
                                <div class="title">资质审核</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">4</div>
                                <div class="title">创建平台应用</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">5</div>
                                <div class="title">开发测试</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">6</div>
                                <div class="title">上架服务市场</div>
                            </div>
                        </li>
                    </ul>
                </div>
                <div>
                        <el-button type="primary" round class="btn-tit">入驻市场服务</el-button>
                    </div>
            </div>
            <div v-if="!type_hidden">
                 <div class="ele-sign-font" v-if="!type_hidden">
                    <span class="ele-sign-block font-black" @click="changetitle">资源优势</span>
                    <span class="ele-sigin-point">·</span>
                    <span class="ele-sign-block" @click="changetitle">接入流程</span>
                </div>
                <div class="ele-sign-type" v-if="title_hidden">
                    <div class="card-first">
                         <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHgAAAB4CAYAAAA5ZDbSAAAACXBIWXMAABYlAAAWJQFJUiTwAAADg0lEQVR42u3cy00bURiG4Q8ra0MJ3nlpSy7AlOC9kTLpgA48dEAHTCSzpwRcAJJnyc50ENOAs+AoiogiZsbnft5Xyo4kBz+aGc/tvzidTqJ8G/ERAEwAE8AEMAFMABPAABPABDABTAATwAQwwJRl3/gIhvfyqitJc/NHkvaS9oupfsWyxgue6BgEO5FUS/r+nx/5KaleTHUAOD3cStK9pMsvfvQo6XYxVZMl8N2jKkmVpKXj32Enqdms3X+QBveh51/7ERLZOvDdoyaSniTNPP8uraTVZu1mtzgQNziyVWCDu++w+3LVUdLcNvKZuEGRbZ8mPQXElfm/nyLElaQH82+lCWyOuTOFb2bWEhNuMGSbW3CleKoixA2CbBN4GRHwMlJc78hcqvSP6xUZ4DC43pABDofrBRngsLjOkUfgBsd1ijwCNwpcZ8gjcKPLKvKoUNxVpLh/I68AHoY7kcLeo+1YY9YKcM9qhb0h0rVLs1aAe7Yqaa1FAb+8ap7I1vtnKzZrBrhjV6WtmStZmVca8KG0NRcFbJ5TfktoyW/nPltd4i66KWmtxQEvpqr18Yht7LVmrQAPqNLHI7axdpSlZ9yKBF5MtZd0HSnyUdK1WSPAmSFbxS3+PDgyZOu4xQNHhOwE1zbwLiK3XULIznBtA8d0ftkksiU7xZXsv124V/j3k9rNevgdGHP35lnu7zo5x3VxDF5FcCw76x6qpy3ZC651YPNe7lxhrhS1svRusGNkb7jWd9GfdteVEh/h4GB37RXXKXAuWUT2jst5sL/ddRBcgP0gB8MF2D1yUFyAhyF3PUtoJc1D4vIl67wvX5WkW/17YaeVdB96wh3AdrEnZgs/xLY2gDOPYzDAlHLOBoLf1O+VPF6q3NZjK19qcpuSa/0YfFO/TxRw2uy2Hh8GwgZdt6spuVaBDW7wabN9kXOdkuviGJzqtNnspuRaBzbH3CimzZq19DnmZjUl19UWXCmeqgLW7R041Wmz2UzJ5Ty4wAAGmAAmgAlgApgAJoABJoAJYAKYACaACWCACWACmAAmgAlgAphsA6c6bTbZKbm+gZuIPqimgHV3yvbbhVFMm93W417TZnOYkuvrGJzqtNnkp+R6ATbv5QadNjvkBfBcpuQ630V/2l1XYoTDl+tOboQDcR5MABPABDABDDABTAATwAQwAUwAA0wAE8AEMAFMZ/Ybhrp2girPRfkAAAAASUVORK5CYII=" alt="">
                         <div class="font1">丰富的 IT 工具</div>
                         <div class="font2">提供测试工具、API 调试工具、服务监控、日志分析统计等丰富的解决方案</div>
                    </div>
                    <div class="card-second">
                         <img src="data:image/png;base64,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" alt="">
                         <div class="font1">沙箱环境</div>
                         <div class="font2">数据独立，支撑开放业务功能测试需求</div>
                    </div>
                     <div class="card-third">
                         <img src="data:image/png;base64,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" alt="">
                         <div class="font1">丰富的 API 接口</div>
                         <div class="font2">提供丰富的 API 接口，涵盖饿了么商家大量的核心功能，为合作伙伴提供多元服务</div>
                    </div>
                </div>
                <div v-if="!title_hidden">
                    <ul class="ele-list">
                        <li>
                            <div>
                                <div class="number">1</div>
                                <div class="title">商务接洽</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">2</div>
                                <div class="title">成为平台服务商</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">3</div>
                                <div class="title">资质审核</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">4</div>
                                <div class="title">创建平台应用</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">5</div>
                                <div class="title">开发测试</div>
                            </div>
                        </li>
                        <li class="icon"></li>
                        <li>
                            <div>
                                <div class="number">6</div>
                                <div class="title">上架服务市场</div>
                            </div>
                        </li>
                    </ul>
                </div>
                <div>
                    <el-button type="primary" round class="btn-tit">查看企业服务商文档</el-button>
                </div>
            </div> 
            </div> 
             <Footer />
        </div>
       
   </div>
</template>

<script>
// import Logo from '../assets/image/logo.png'
import Header from '../components/Header'
import Footer from './Foot'
export default {
  name: 'Eleme',
  data(){
      return{
          position:true,  //true是在左面， false是在有面
          ele_left:423,     //位置信息
          title_hidden:true, //true是资源优享，flase是接入流程
          type_hidden:true, //true是平台服务商， flase是企业服务商
          white_hidden:true, //控制白点儿的位置,true是左边
      }
  },
  components:{
      Header,
      Footer
  },
  methods:{
    //   移动白块
      moveWhite(){
        // 通过改变position来控制白块的移动
        this.position = !this.position
        this.title_hidden = true //每点击一次刷新 资源优享的状态
        this.type_hidden = !this.type_hidden //每点一次刷新平台服务状态
        if(this.position){
            // 添加计时器 在计时器中调用左移函数，当left达到423时清除计数器，停止移动
             let timer = setInterval(()=>{
                let sign = this.subleft()
                if( sign<= 423){
                    clearInterval(timer)
                }
            },1)
        }else{
            let timer = setInterval(()=>{
            // 同上
                let sign = this.addleft()
                if( sign>= 710){
                    clearInterval(timer)
                }
            },1)
        }
        
      },
    //  向右移动
      addleft(){
        //   通过增加元素的left属性，让白块右移
          let ele = document.getElementsByClassName("ele-body-move")[0];
          let {ele_left} = this
          ele_left++
          this.ele_left = ele_left
          ele.style.left = ele_left+"px"
          return ele_left
      },
    //  向左移动  
      subleft(){
        //  通过减少元素的left属性，让白块左移
          let ele = document.getElementsByClassName("ele-body-move")[0];
          let {ele_left} = this
          ele_left--
          this.ele_left = ele_left
          ele.style.left = ele_left+"px"
          return ele_left
      },
    //  控制简介显示
      changetitle(){
        //   控制资源优势和接入流程显示,同时控制字体颜色
        this.title_hidden = !this.title_hidden 
        let ele = document.getElementsByClassName("ele-sign-block");
        // 将font-black的样式全部清除
        console.log(ele)
        ele[1].classList.remove("font-black") 
        ele[0].classList.remove("font-black")
        //根据title_hidden进行添加font-black样式
        if(this.title_hidden){
            ele[0].classList.add("font-black")
        }else{
            ele[1].classList.add("font-black")
        }
      },
    // 控制白点儿
    clickpoint(){
        this.white_hidden = !this.white_hidden;
        let point1 = document.getElementsByClassName("point1")[0]
        let point2 = document.getElementsByClassName("point2")[0]
        console.log(point1.classList.add)
        point1.classList.remove("point-white")
        point2.classList.remove("point-white")
        if(this.white_hidden){
            // setActiveItem(0)
            point1.classList.add("point-white")
            this.$refs.carousel.setActiveItem(0)
        }else{
            // setActiveItem(1)
            point2.classList.add("point-white")
            this.$refs.carousel.setActiveItem(1)
        }
    }
  }
}
</script>

<style scoped>

    *{
        list-style: none;
    }
    .point1, .point2{
        width: 10px;
        height: 10px;
        background-color: #eee;
        border-radius: 25px;
        float: left;
        margin:5px;
        cursor: pointer;
        opacity: 70%;
    }
    .point-contorl{
        position:absolute;
        top: 500px;
        z-index: 99;
        margin: 0 auto;
        text-align: center;
        left: 49%;
    }
    .point-white{
        background-color: white;
        opacity: 100%;
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
        height: 550px;
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
        position: absolute;
        top:0;
        height: 550px;
        width: 100%;
    }
    .tini-box{
        width: 100%;
        height: 100px;
        background-size: 100% 100%;
    }
    .header-carousel{
        height: 550px;
    }
    .header-title{
        position: relative;
        top:30%;
        color: white;
        text-align: center;
    }
    .header-title-1{
        margin-bottom: 50px;
        font-size: 40px;
        font-weight: 900;
    }
    .header-title-2{
        margin-bottom: 50px;
        font-size: 20px;
        font-weight: 500;
    }
    .btn-add2{
        width:180px;
        height:45px;
        font-size: 18px;
        background-color:white;
        border-color: white;
        color:#00c8ff;
        margin-top:50px;

    }
    .btn-add1{
        width:180px;
        height:45px;
        font-size: 18px;
        background-color:white;
        border-color: white;
        color:#7480db;
        margin-top:50px;
    }
    .adv{
        position: absolute;
        top:550px;
        border-bottom: 0.1px solid #d9d9d9;
        width: 100%;
        text-align: center;
        

    }
    .adv li{
        float:left;
        margin:10px;
        margin-left: 12.5%;
        cursor: pointer;
    }
    .adv-new ,.adv-content, .adv-all{
        color:#cccccc;
        font-size: 14px
    }
    .adv-new{
        width: 40px;
        height: 15px;
        background-color:#6aa84f;
        font-size:10px;
        border-radius: 25px;
        color: white;
        
    }
    .adv-new-fitin{
        margin: 0 5px;
        font-style:italic;
    }
</style>

<style scoped>
.header-carousel /deep/ .el-carousel__container{
      height: 550px!important;
  }
</style>

<style scoped>
.ele-body{
    position: absolute;
    top:590px;
    width: 100%;
    height: 1800px;

}
.ele-body-title{
    font-weight: 900;
    font-size:30px;
    text-align: center;
    padding-top: 120px;
    color:#636363;
}
.ele-body-choose{
    text-align: center;
    width: 600px;
    height: 50px;
    vertical-align:middle;
    background-color: #d6edff;
    border-radius: 25px;
    position: relative;
    top:60px;
    margin:0 auto;
}
.ele-body-title-1{
    position: relative;
    top:25%;
    font-size:20px;
    font-weight: 500;
    z-index:20;
    cursor: pointer;
}
.ele-body-title-2{
    position: relative;
    top:22.5%;
    font-weight: 300;
    font-size:12px;
    margin:0 15px;
    z-index:20;
    cursor: pointer;
}
.ele-body-fitin{
    width: 30px;
    height: 50px;
    background-color: #d6edff;
    border-radius: 25px;
    color:#d6edff;
}
.ele-body-move{
    display: block;
    position: absolute;
    width: 299px;
    height: 48px;
    background-color:white;
    border-radius: 25px;
    top:222.5px;
    float: left;
    left: 423px;
    /*415 - 710 */
    z-index:10;
}
.ele-sign{
    position: relative;
    top:80px;
    margin:0 auto;
    text-align: center;
    
}
.card-first, .card-second, .card-third{
    float: left;
    width: 300px;
    margin:0 auto;
    position: relative;

    
}
.card-first>img, .card-second>img, .card-third>img{
    width: 50px;
    height: 50px;
    margin:20px;
}
.ele-sign-type{
    display: flex;
    padding: 0 100px;
    float:top;
}
.ele-sign-font{
    color:#cccccc;
    cursor: pointer;
}
.ele-sign-block{
    margin:20px
}
.ele-sigin-point{
    font-size:20px
}
.font1{
    font-size: 24px;
    color:#a0a0a0;
    margin:20px
}
.font2{
    font-szie:16px;
    color: #ccc;
}
.font-black{
    color:#444;
}
.ele-list{
    display: flex;
    margin:0 auto;
    text-align: center;
    position: relative;
    justify-content: center;
    padding: 0 100px;
}
.ele-list li{
    float:left;
    margin:20px;
    position: relative;
}
.icon{
    width:40px;
    height: 40px;
    margin:0;
    border-top: 1px solid #e6ebf5;
    border-right: 1px solid #e6ebf5;
    transform: rotate(45deg);
}
.number{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: solid 2px #5d80f5;
    margin: 0 auto;
    line-height: 40px;
    color: #5d80f5;
    margin-bottom: 28px;
}
.title{
    color:#566166;
}
.btn-tit{
    width:200px;
    height:45px;
    font-size: 18px;
    background-color:#7480db;
    border-color: white;
    color:white;
    margin-top:50px;
    text-align: center;
}
</style>
