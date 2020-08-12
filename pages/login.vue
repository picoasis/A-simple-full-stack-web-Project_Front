<template>
    <div>
        <div class='title-line'>
            <span class='tit'>注册/登录</span>
        </div>
        <el-form class="login-form" :rules="rules">
            <el-form-item props="email">
                <el-input placeholder="你的邮箱"></el-input>
            </el-form-item>
            <el-form-item props="password">
                <span>
                </span>
                <el-input placeholder="密码"></el-input>
            </el-form-item>
            <el-form-item props="captcha">
                <img @click="updateCaptcha" :src="captchaUrl" alt=""/>
                <el-input placeholder="请输入图片验证码"></el-input>
            </el-form-item>
        </el-form>
    </div>
</template>
<script>
export default {
  layout: "login",
  data(){
    return {
        rules:[],
        captchaUrl:"/api/captcha?_t=" + new Date().getTime(),
    }
  },
  methods:{
    updateCaptcha(){
        this.captchaUrl = "/api/captcha?_t=" + new Date().getTime(); 
    }
  }
}
</script>
<style lang="stylus">
.title-line
    height 28px
    width 980px
    margin 0 auto
    text-align center
    border-bottom 1px solid #dddddd
    margin-bottom 28px
    .tit
        font-size 38px
        height 56px
        line-height 56px
        margin 0 auto
        padding 0 20px
        text-align center
        background-color #fff
.login-form
  width 400px
  margin 0 auto 
</style>
