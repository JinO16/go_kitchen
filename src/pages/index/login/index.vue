<template>
  <view class="content">
    <image class="login-logo" src="/static/img/login.png" mode="aspectFit" />
    <view class="login-title">厨圈App</view>
    <view class="login-form">
      <input class="login-input" placeholder-class placeholder="请输入用户名" />
      <input class="login-input" placeholder-class password placeholder="请输入密码" />
      <view class="login-label">忘记密码？</view>
      <button class="login-btn" @click="handleLogin">立即登录</button>
      <navigator url="../register/index" hover-class="none" class="login-label">还没有账号？点此注册.</navigator>
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
  onLoad() {
    //生命周期函数，相当于mounted
  },
  methods: {
    handleLogin() {
      console.log("登录");
      //---需要调用接口----
      uni.switchTab({
        url: "../home/kitchenCircle/index"
      });
    }
  }
};
</script>
<style scoped>
@import "../../../static/style/loginCommon.css";
</style>
