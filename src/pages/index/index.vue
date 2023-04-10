<template>
    <view relative w-full>
        <NavigationBar />
        <view style="padding: 0 35rpx 0 35rpx" box-border overflow-hidden>
          <view>
            <IndexSwiper :banner-list="bannerList" />
            <Category />
          </view>
        </view>
      </view>
</template>

<script setup lang="ts">
import {getCardList, getBannerList} from "@/api/home"
import NavigationBar from "./components/NavigationBar.vue"
import Category from './components/Category.vue'
components:{
  NavigationBar
}
let bannerList = $ref<string[]>([])
let cardList = $ref<any[]>([])

onLoad(()=>{
  bannerList = getBannerList().data[0].imgUrl.split(",").map(i=>i.replace("\n",""))
  cardList = getCardList().data

  
})
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
