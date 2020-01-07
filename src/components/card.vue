<template>
  <view class="cardBox">
    <el-row>
      <el-col :span="11" v-for="item in cardData" :key="item.id" :offset="1" style="margin-top:10px">
        <el-card :body-style="{ padding: '0px' }">
          <img :src="item.imageUrl" class="card-image" />
          <view style="padding: 14px;">
            <span>{{ item.title }}</span>
            <view class="bottom clearfix">
              <time class="time">{{ item.currDate | formateDate }}</time>
              <el-button type="text" class="button" @click="handleDetail(item)">查看详情</el-button>
            </view>
          </view>
        </el-card>
      </el-col>
    </el-row>
  </view>
</template>
<script>
import dayjs from "dayjs";
export default {
  data() {
    return {};
  },
  props: {
    cardData: {
      type: Array,
      default: function(value) {
        return [];
      }
    }
  },
  filters: {
    formateDate(date) {
      return dayjs(date).format("YYYY-MM-DD HH:mm:ss");
    }
  },
  onLoad() {},
  methods: {
    //点击查看详情
    handleDetail(value) {
      const t = this;
      t.$emit('handleDetail',value)
    }
  }
};
</script>
<style scoped>
.cardBox {
  margin: 0px 12px 20px 0px;
}
.time {
  font-size: 13px;
  color: #999;
}

.bottom {
  margin-top: 13px;
  line-height: 12px;
}

.button {
  padding: 0;
  float: right;
  margin-top: 10px;
}

.card-image {
  width: 100%;
  display: block;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both;
}
</style>
