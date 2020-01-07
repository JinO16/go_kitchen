<template>
  <view class="content">
    <image class="login-logo" src="/static/img/register.png" mode="aspectFit" />
    <view class="login-title">厨圈App</view>
    <view class="login-form">
      <input class="login-input" placeholder-class placeholder="请输入用户名" />
      <input class="login-input" placeholder-class password placeholder="请输入密码" />
      <input class="login-input" placeholder-class password placeholder="请确认密码" />
      <button class="login-btn" @click="handleRegister">立即注册</button>
      <navigator url="../login/index" hover-class="none" class="login-label">已有账号？点此去登录.</navigator>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      //   title: "登录页面"
    };
  },
  onLoad() {},
  methods: {
    handleRegister() {
      console.log("注册");
      uni.redirectTo({
        url: "../login/index"
      });
    }
  }
};
</script>

<style scoped>
@import "../../../static/style/loginCommon.css";
</style>
