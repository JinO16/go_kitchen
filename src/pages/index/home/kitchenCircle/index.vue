<template>
  <view class="content">
    <view class="search-input">
      <el-input placeholder="请输入内容" prefix-icon="el-icon-search" v-model="searchInput" @input="handleSearch"> </el-input>
    </view>
    <card :cardData="cardData" @handleDetail="handleDetail"> </card>
  </view>
</template>

<script>
import Card from "../../../../components/card";
export default {
  data() {
    return {
      searchInput: "",
      //card数据
      cardData: [
        {
          id: 1,
          imageUrl: "https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png",
          content: "唯有美食与爱，不可辜负",
          title: "汉堡",
          currDate: new Date()
        },
        {
          id: 2,
          imageUrl: "../../../../static/img/美食1.png",
          content: "唯有美食与爱，不可辜负",
          title: "美食",
          currDate: new Date()
        },
        {
          id: 3,
          imageUrl: "../../../../static/img/美食2.png",
          content: "唯有美食与爱，不可辜负",
          title: "美食",
          currDate: new Date()
        }
      ]
    };
  },
  components: {
    Card
  },
  onLoad() {
    //生命周期函数，相当于mounted
  },
  methods: {
    //搜索框内容
    handleSearch(value) {
      console.log("搜索内容---->", value);
    },
    //进入详情页面
    handleDetail(params){
      const cardId = JSON.parse(params.id);
      uni.navigateTo({
        url:`./detail?params= ${cardId}`
      })
    
    }
  }
};
</script>
<style scoped>
.search-input {
  margin: 10px 12px 0px;
}
</style>
