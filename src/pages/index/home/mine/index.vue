<template>
  <view class="content-box">
    <view class="header">
      <view class="header-profily"></view>
      <text>傻不拉几</text>
      <image src="../../../../static/img/mine/设置.png" @click="handlePersonEdit" />
    </view>
    <view class="status-list">
      <view class="status" v-for="(item,key) in status" :key="key">
        <image class="icon" :src="item.url" mode="aspectFit" />
        <text>{{item.name}}</text>
      </view>
    </view>
    <view class="status-menu">
      <view class="menu-item" v-for="(item,key) in menus" :key="key">
        <image :src="item.url" mode="aspectFit" />
        <text>{{item.name}}</text>
      </view>
    </view>
    <button class="exit-btn" @click="handleExitLogin">退出登录</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      status: [
        {
          key: 1,
          name: "浏览记录",
          url: "../../../../static/img/mine/浏览记录.png"
        },
        {
          key: 2,
          name: "我的收藏",
          url: "../../../../static/img/mine/收藏.png"
        },
        {
          key: 3,
          name: "我的订单",
          url: "../../../../static/img/mine/我的订单.png"
        },
        {
          key: 4,
          name: "我的发布",
          url: "../../../../static/img/mine/我的发布.png"
        }
      ],
      menus: [
        {
          key: 1,
          name: "地址管理",
          url: "../../../../static/img/mine/地址管理.png"
        },
        {
          key: 2,
          name: "帮助中心",
          url: "../../../../static/img/mine/帮助中心.png"
        },
        {
          key: 3,
          name: "意见反馈",
          url: "../../../../static/img/mine/意见反馈.png"
        },
        {
          key: 4,
          name: "关于",
          url: "../../../../static/img/mine/关于.png"
        }
      ]
    };
  },
  onLoad() {
    //生命周期函数，相当于mounted
  },
  methods: {
    //编辑个人资料
    handlePersonEdit() {
      console.log("编辑个人资料");
      uni.redirectTo({
        url: "../mine/edit"
      });
    },
    //退出登录
    handleExitLogin() {
      console.log("退出登录");
      // uni.redirectTo({
      //   url: "../../login/index"
      // });
    }
  }
};
</script>
<style scoped>
.content-box {
  padding: 30px;
}
.header {
  display: flex;
  align-items: center;
  border-bottom: 2px solid #f6f6f6;
  padding-bottom: 35rpx;
  position: relative;
}
.header-profily {
  height: 120rpx;
  width: 120rpx;
  background-image: url("../../../../static/img/mine/头像.jpg");
  background-size: 100%;
}
.header text {
  margin-left: 20px;
  font-size: 30rpx;
}
.header image {
  position: absolute;
  height: 40rpx;
  width: 40rpx;
  right: 0;
  top: 0;
}

.status-list {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
}
.status {
  width: 140rpx;
  font-size: 24rpx;
  text-align: center;
  letter-spacing: 0.5px;
  display: flex;
  flex-direction: column;
}
.icon {
  width: 50rpx;
  height: 50rpx;
  margin: 0 auto;
  margin-bottom: 5px;
}
.status-menu {
  width: 100%;
  display: inline-block;
  margin-top: 30px;
}
.menu-item {
  font-size: 28rpx;
  letter-spacing: 1px;
  padding: 14px 5%;
  background-color: #fefefe;
  overflow: hidden;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  position: relative;
  border-bottom: 1px solid #efefef;
}
.menu-item:hover {
  background-color: #f6f6f6;
}
.menu-item::after {
  content: "";
  width: 30rpx;
  height: 30rpx;
  position: absolute;
  right: 5%;
  background: url("../../../../static/img/mine/right.png");
  background-size: 100%;
}
.menu-item text:nth-of-type(1) {
  margin-left: 10px;
}
.menu-item image {
  width: 40upx;
  height: 40upx;
}
.exit-btn {
  background-color: #ff4500;
  color: #ffffff;
  border: 0;
  border-radius: 100rpx;
  font-size: 36rpx;
  margin-top: 30rpx;
}
</style>
