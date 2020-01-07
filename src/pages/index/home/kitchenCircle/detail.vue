<template>
  <view class="content">
    详情页面
  </view>
</template>
<script>
export default {
    data(){
        return{

        }
    },
    onLoad(options){
     console.log('传过来的参数---->',options.params);
    //根据传过来的id，调用接口，获取该卡片的数据
    }
}
</script>
