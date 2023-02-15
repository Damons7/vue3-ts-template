<script setup lang="ts">
import { ref } from "vue";
const checkNav=(item:object)=>{
 
}
const getPlayNum = (num: number) => {
  return num / 10000 >= 1
    ? (num / 10000).toFixed(2) + "w"
    :  num;
};

const navList = [
  {
    name:"推荐",
  },
  {
    name:"排行",
  },
  {
    name:"分类",
  }
]

// 默认项
const actNav = ref(navList[0])

const list = [
  {
    img: "https://img2.baidu.com/it/u=345670089,3951600800&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
    name: "修罗武神",
    type: "玄幻",
    number: 111,
    playNum: getPlayNum(744),
  },
  {
    img: "https://img2.baidu.com/it/u=345670089,3951600800&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
    name: "修罗武神2",
    type: "玄幻2",
    number: 744,
    playNum: getPlayNum(12535),
  },
  {
    img: "https://img2.baidu.com/it/u=345670089,3951600800&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
    name: "修罗武神3",
    type: "玄幻3",
    number: 213,
    playNum: getPlayNum(6666),
  },
];
</script>

<template>
  <view class="header flex-between">
    <view class="header-left">
      <img
        src="https://s1.hdslb.com/bfs/manga-static/manga-mobile/static/img/827fd99e14bb260.png"
        alt=""
        class="logo"
      />
      <view class="nav">

        <view class="nav-item nav-item-act" v-for="item in navList" @tap="checkNav(item)">
        {{ item.name }}</view>
      </view>
    </view>
    <view class="header-right">
      <view class="download flex-center">下载哔哩哔哩漫画</view>
    </view>
  </view>
  <view class="body">
    <view class="swiper"></view>
    <view class="m-list">
      <view class="m-item" v-for="(item, index) in list.concat(list)" :key="index">
        <img :src="item.img" alt="" class="m-item-img" />
        <view class="m-item-name">
          <view class="m-item-name-text">{{ item.name }}</view>
          <span class="m-item-name-mark">{{ item.type }}</span>
        </view>
        <view class="m-item-detail flex-between">
          <view class="m-item-number">{{ item.number }}</view>
          <view class="m-item-play">
            <img
              alt=""
              src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgaGVpZ2h0PSIxNiI+PHBhdGggZmlsbD0iI0QyRDZEOSIgZmlsbC1ydWxlPSJldmVub2RkIiBkPSJNMiAyaDEyYTEgMSAwIDAxMSAxdjlhMSAxIDAgMDEtMSAxSDkuNWwtMi43MSAxLjkzNWEuNS41IDAgMDEtLjc5LS40MDdWMTNIMmExIDEgMCAwMS0xLTFWM2ExIDEgMCAwMTEtMXptMy41IDQuNmg1YS42LjYgMCAwMDAtMS4yaC01YS42LjYgMCAxMDAgMS4yem0wIDNoM2EuNi42IDAgMTAwLTEuMmgtM2EuNi42IDAgMTAwIDEuMnoiLz48L3N2Zz4="
              class="m-item-icon"
            />
            <view class="m-item-playNum">
              {{ item.playNum }}
            </view>
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<style scoped lang="less">
.flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
.flex-between {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header {
  position: sticky;
  top: 0;
  z-index: 100;
  height: 46px;
  background-color: #fff;
  font-size: 16px;
  border-bottom: 1px solid #ddd;
  padding: 0 20px;
  .header-left {
    display: flex;
    align-items: center;
    .logo {
      width: 26px;
      height: 26px;
      padding-right: 20px;
    }
    .nav {
      display: flex;
      .nav-item {
        display: inline-block;
        margin: 0 8px;
        color: #90959b;
      }
      .nav-item-act {
        color: #fb7299;
      }
    }
  }
  .header-right {
    .download {
      background: #fb7299;
      border-radius: 15px;
      font-size: 12px;
      color: #fff;
      padding: 4px 16px;
    }
  }
}
.body {
  .swiper {
  }
  .m-list {
    display: flex;
    flex-direction: column;
    .m-item {
      padding: 0 16px 20px;
      border-color: #fb7299;
      .m-item-img {
        width: 100%;
        max-height: 192px;
      }
      .m-item-name {
        display: flex;
        align-items: center;
        .m-item-name-text {
          font-size: 20px;
          color: #212121;
          max-width: 280px;
          overflow: hidden;
        }
        .m-item-name-mark {
          margin-left: 7px;
          color: rgb(144, 149, 155);
          background: rgba(192, 192, 192, 0.16);
          padding: 1px 4px;
          border-radius: 5px;
          font-size: 12px;
        }
      }
      .m-item-detail {
        margin-top: 2px;
        .m-item-number {
          font-size: 14px;
          color: #999;
        }
        .m-item-play {
          display: flex;
          align-items: center;
          .m-item-icon {
            width: 16px;
            height: 16px;
            margin-right: 4px;
          }
          .m-item-playNum {
            font-size: 14px;
            color: #999;
          }
        }
      }
    }
  }
}
</style>
