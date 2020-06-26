<template>
    <div class="myfooter">
        <div class="serve-plaform">
            <div class="serve-adv">平台优势</div>
            <div class="serve-img">
                <ul class="serve-ul">
                    <li class="serve-li1">
                        <div>
                            <img class="my-img" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKAAAACgCAYAAACLz2ctAAAACXBIWXMAABYlAAAWJQFJUiTwAAAIVUlEQVR42u2dP2wb1x3HvyIk6w9InQSrqTMIsQHbQpyFRTrZMMwk9JB0CINoyCYVzFwza4uC1Nyh1JiBqAV0VGF6SDuYsWUI9lS3GooIUgTEQYCmdR2IJxKWZRtShzvaFEVSlHX3SB4/H0AA9d4dJL730e/e73ePp769vT0BtIsQQwAICAgIgICAgAAICAgIYIJ+hiAgrM2dlpSRlJBkua22pLykjKbSDzvx1+6jEB0I+aKSlqrEq8WWFNNUegUBwY/ItyLJejZ8XuWxq9rtdzwMvbAVLt7Sie31ioTRTouErAG7n0xFvq2J6ZfySdJuv6WtiWk9Gz4vNzpmSELAaxKSVB672vCAqr4EAoLXWJVo14iqPgsBARAwUNiVhKPhJL/qsxEQvCYvSeHirYYHVPXlERD8yILtE9vrGn28uC8Shl7YGn28WF2G6bgsmDpgEOjiQjQRMAg4YkUlLdSs82y3LdqJ8hEBoe0Y34yQK5RiklKSPq7puikpm4xHlpiW3sFoBMwVSllJ1w45bD4Zj6SYGgT0Wr7rkmZaPBwJEdDzy+6dI572Hpfj4GMqC04ZOgeIgHUjIKl2Z2HLqRvmJeWT8Ugx6BEQOgtLThXiT5Ie5gqlFAJCO2X8o5skIiC0jZl2SGhqDZjXwcLzYdxMxiMJvPBlPmKSZlW/LPZFMh7JBi0CZg2dAy2QjEeWkvHIrKRf6OAewUyuUBoLlIBuPW/+CKcsUAM0Mi8rkmJ11oSJQAnovtlUixLOu3+dYE7ChZrm4AlYJeF7cjYeHFjzybn7QQHaPLXJRyxQSQh0RWKyVxMs+gIXAQEQEBAQAAEBAQEQEBAQEBCgLXTnM6LX5hJyNiu8xRRKkr6XlNJUOt9tv3ioS+W7gXz7eEvSDXdsENBn2KYVoLEJdelfOwRkbEhCAAGBLLjreWJd1pPRy5Kkka1ljdjLnvZDJ0fAtbms1uaW3AclVtqibpuRhXFFntrXXvVDZ0fAqKQrkpa0Nhdz25bUgf8WAIK5BkzJ+XSVJWnZ/bLcNiNb7Ee2luu+9qof/MG7LfnO5XdZUthtKUu67PmjYdfm+AxBM6bSr7WVni35wCX4mNFvyY1+Zfcr7K4Jowwz+B0Bs1VrvsvuV2VNyK0z8D0LXnmZjFTWfE42nK3qA/BJwKl0qk5bvcc+APgSAY3xePK3zFoTJnp0DQiAgICAAMFeA/7uD+vMWhO+TL/zuqdWymaV10RAMErlfr6x+/ddGQHBH5LxyHUdfE4gERBIQgAQEBAQAAE7jQvnwvr8s0ldOBdmMMiCzTI0GNKnH57S0GBIm/ZzffNtmUEhAprjg0snNTToDGFx6zkDgoDmODM5oovvjr/8fvvpLoOCgOb41fs/2/f9j492GBQENMPFd8f15huDDAQCmmfcGtAHl04eaP/uhycMDgKaufRWEg9AQOOJx9tnD9b7WP8hoO8MDYY0/dHP6/Y93SEDRkCfufTLcY2NDtTt27SpASKgz4nH+xdPNuynCI2AvvLph6ea9lOERkDfuHAurDOTw02PIQlBQN8Sj8Oin0Rp5jiwG6YJ1ZsNmvHmG4P6/W/OHnrc6kZZf77xbwaWCKiWpKrebOAFb58Na9waYHAR8PiJx+uwulGmZIOAh+PHZoOnO7v66vb/GFwEPDzxqLfZ4Lh8fe8noh8CHs70R6c8z2h/fLSj+w82GVwEbM64NVB3s8Fx4dKLgC2xaT/X6oa3Hyy6/2CTvYJNMFYHzBVKs3r1wPKU+yySjqOVOt3QYEiffzZ5aKLydGdXX9/7Ccs6JAJWnqTf9U/ObzWj/er2I7ZqdZCAVoPXXclh0e+7H7b1j39tYRhrQH8YHmo+dH/5238YJAT0j0abUyXp9n1qfgjoM43u6Ra3nuve36n5IaDPNCpWL/71vyQeCNieJGR1o0zNDwHbA5sNENAYZyZHDrSx2QAB2wabDRCwres/Lr0IaJTqIjSbDRDQOJUiNJsNjg+finsNVjfKGrcGdP/BZvBrfmtzY5Lykq64LXclJTSVLiJgm/jm23IvPZC8Wj65r/OSYlyCwQRX6ratzZ1GQGgfU+mHCAgmuNtiW88I+D1OGB2bRI1wd922ns2CU5Ju4FrDsfH6Ulv0KuEIRAT8Mv1OXtInRMIDke8Td2y6ir69vT0jPyhXKO37Qcl4pA9vgCQEEBAQEAABAQEBEBAQEAABIfiYvBVnq+qhRLlCKZaMR5aYArPkCqWYnFt2H9d03ZSUNT0nJiNg7RubRQfj8mUl3akjn9y2O+4xgRSw9j7lTK5QiqKFMfmuS7rWwqHXTEpoWkC7NioiobHL7swRTrnmnhMcAZPxSFFSpqbZkvTPXKF03dQb7lFShs45MsZ2w9RcCmZwovMxsWMp1IY3NStpgentikv36cAJWCXhF3XWhNBZEfBhIAV031xW0mlJv5ZTg0LGHsT4GhDacinNq37trxk3k/FIwu/fjVtxvUHW0DkICHWXO0uS5o9wyoKpW3II2DsSplqUcN5NEgO+BnSeLZKR8yHnyiYFW84dk4xXj36AA+vBmDpoM0J7BFybi8rZnNDoX3bZkmKaSq+gDFmwH5FvRZL1bPi8ymNXtdvveBh6YStcvKUT2+sVCaNEwmDTjjVgpiLf1sT0S/kkabff0tbEtJ4Nn5cbHTNMEQJ6TUKSymNXGx5Q1ZdgihDQa6xKtGtEVZ/FFCEgQKAEtCsJR8Nf6lUf94cR0HPykhQu3mp4QFVfnilCQD+yYPvE9rpGHy/ui4ShF7ZGHy9Wl2HIggMOhWjowSTEESsqZ2e0XSPegpwCNPIRAQGCGAEBEBAQEBCQIQAEBAQEQEBAQAAEhJ7h/645v+8MQbifAAAAAElFTkSuQmCC" alt="">
                            <div class="my-title">
                                <div class="my-sign">线上快速对接</div>
                                <div class="my-content">提供完善的线上对接服务，无需咨询客服，开发者可无缝、便捷、高效地接入服务。</div>
                            </div>
                        </div>
                    </li>
                    <li class="serve-li2">
                        <div>
                            <img class="my-img" src="data:image/png;base64,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" alt="">
                            <div class="my-title">
                                <div class="my-sign">业务深度开放</div>
                                <div class="my-content">基于商家需求，提供店铺、商品、订单、配送等业务在内的丰富接口。</div>
                            </div>
                        </div>
                    </li>
                    
                </ul>

                <ul class="serve-ul">
                    <li class="serve-li1">
                        <div>
                            <img class="my-img" src="data:image/png;base64,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" alt="">
                            <div class="my-title">
                                <div class="my-sign">完善的服务支持</div>
                                <div class="my-content">提供稳定的沙箱测试环境和 7*24 小时自助测试服务，有完善的应用监控、服务告警。</div>
                            </div>
                        </div>
                    </li>
                    <li class="serve-li2">
                        <div>
                            <img class="my-img" src="data:image/png;base64,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" alt="">
                            <div class="my-title">
                                <div class="my-sign">在线问答社区</div>
                                <div class="my-content">直接面对饿了么开发者，沟通更加有效，提问更加直接。</div>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
            <div class="logomuch">
                <img src='../assets/image/logomuch.png' />
                 <div class="endtwo">
                    <div class="endtwo-text">成就行业先锋典范，从加入饿了么开发者行列开始</div>
                    <el-button type="primary" round class="btn-add1">立即免费加入</el-button>
                </div>
                 <div>
           <div class="logo-padding">
            <div class="logo-main">
                <ul>
                    <li><img src="../assets/eleme.png" class="eleme"></li>
                    <li>联系我们</li>
                    <li>
                        <p>
                        ISV 商务接洽<br/>
                        sm.merchant@ele.me <br/><br/>

                        © ele.me 2020
                        </p>
                    </li>
                </ul>
            </div>
            <div class="logo-main">
                <ul>
                    <li class="logo-main-title">开发文档</li>
                    <li>
                        <p class="ele-p">
                            平台说明<br/><br/>
                            授权说明<br/><br/>
                            消息推送<br/><br/>
                            如何测试<br/><br/>
                            常用工具<br/><br/>
                            SDK使用说明<br/><br/>
                            权限属性调整<br/><br/>
                            用户身份说明<br/><br/>
                        </p>
                    </li>
                </ul>
            </div>
            <div class="logo-main">
                <ul>
                    <li class="logo-main-title">运营规范</li>
                </ul>
                    <li>
                        <p class="ele-p">
                            平台说明<br/><br/>
                            授权说明<br/><br/>
                            消息推送<br/><br/>
                            如何测试<br/><br/>
                            常用工具<br/><br/>
                            SDK使用说明<br/><br/>
                            权限属性调整<br/><br/>
                            用户身份说明<br/><br/>
                        </p>
                    </li>
            </div>
            <div class="logo-main">
                <ul>
                   <ul>
                    <li class="logo-main-title">服务支持</li>
                </ul>
                    <li>
                        <p class="ele-p">
                            平台说明<br/><br/>
                            授权说明<br/><br/>
                            消息推送<br/><br/>
                            如何测试<br/><br/>
                            常用工具<br/><br/>
                            SDK使用说明<br/><br/>
                            权限属性调整<br/><br/>
                            用户身份说明<br/><br/>
                        </p>
                    </li>
                </ul>
            </div>
        </div>  
        </div>      
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{}
    },
    
}
</script>
<style scoped>
*{
    list-style: none;
}
.myfooter{
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 1100px;
}
.serve-plaform{
    width: 100%;
    height: 500px;
    background-color: #ebf5fa;
}
.serve-adv{
    position: relative;
    top:60px;
    margin: 0 auto;
    font-size: 27px;
    font-weight: 500;
    text-align: center;
    
}
.serve-img{
    position: relative;
    top: 100px;
}
.my-img{
    width: 70px;
    height: 70px;
    margin:20px;
    float: left;
}
.my-title{
    width: 380px;
    color: #999;
}
.my-sign{
    color:#999;
    margin:20px 0 ;
}
.my-content{
    font-size: 14px;
}
.serve-li1{
    float: left;
    margin-left: 15%;
}
.serve-li2{
    float: right;
    margin-right: 15%;
}
.logomuch{
    width:100%;
    height: 200px;
    position: relative;
    top:200px;
}
.logomuch img{
    width:100%;
}
.endtwo{
    background-image: url('../assets/image/back1.jpg');
    padding-top:30px ;
    width: 100%;
    height: 200px;
    text-align: center;
    background-size: 100% ;
    color:#f5f7fa;
    font-weight: 500;
    font-size: 17px;
}
.endtwo-text{
    margin: 30px 0;
}
.eleme{
    width:100px !important;

}
.ele-p{
    margin:20px auto;
}
.logo-main{
    font-size: 14px;
    color:#aaa;
    float: left;
    margin:5% 5%;

}
.logo-padding{
   height: 400px;
   padding: 0 25%;
   background-color:#f5f7fa;
}
.logo-main-title{
    font-size: 16px;
    color:#444;
    font-weight: 600;
}
</style>