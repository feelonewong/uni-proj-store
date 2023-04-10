<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text color-red text-50>{{ title }}</text>
    </view>
    <view @click="handleChange">改变元素</view>
  </view>
</template>

<script setup lang="ts">
let title = $ref('Hello')
onLoad(()=>{
  title = "123"
})

let {isLogin} = $(useUser())
console.log('isLogin---1', isLogin)

const  handleChange = () =>{
  isLogin = true
  console.log('isLogin---2', isLogin)
}

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
