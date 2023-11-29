<template name="skeleton">
  <view class="sk-container">
    <scroll-view :scroll-y="true" class="viewport" :enable-back-to-top="true">
      <view class="goods">
        <view class="preview">
          <swiper :circular="true" :current="0" :autoplay="false">
            <swiper-item
              style="
                position: absolute;
                width: 100%;
                height: 100%;
                transform: translate(0%, 0px) translateZ(0px);
              "
            >
              <image mode="aspectFill" class="sk-image"></image>
            </swiper-item>
          </swiper>
          <view class="indicator">
            <text class="current sk-transparent sk-opacity">1</text>
            <text class="split sk-transparent sk-opacity">/</text>
            <text class="total sk-transparent sk-opacity">5</text>
          </view>
        </view>
        <view class="meta">
          <view class="price">
            <text class="symbol sk-transparent sk-opacity">¥</text>
            <text class="number sk-transparent sk-text-14-2857-992 sk-text">1480.00</text>
          </view>
          <view class="name ellipsis sk-transparent sk-text-14-2857-232 sk-text"
            >法国年份雅文邑700毫升</view
          >
          <view class="desc sk-transparent sk-text-0-0000-617 sk-text"
            >经典产区限量单一老年份app</view
          >
        </view>
        <view class="action">
          <view class="item arrow sk-pseudo sk-pseudo-circle">
            <text class="label sk-transparent sk-text-14-2857-550 sk-text">选择</text>
            <text class="text ellipsis sk-transparent sk-text-14-2857-731 sk-text">
              请选择商品规格
            </text>
          </view>
          <view class="item arrow sk-pseudo sk-pseudo-circle">
            <text class="label sk-transparent sk-text-14-2857-638 sk-text">送至</text>
            <text class="text ellipsis sk-transparent sk-text-14-2857-262 sk-text">
              请选择收获地址
            </text>
          </view>
          <view class="item arrow sk-pseudo sk-pseudo-circle">
            <text class="label sk-transparent sk-text-14-2857-919 sk-text">服务</text>
            <text class="text ellipsis sk-transparent sk-text-14-2857-759 sk-text">
              无忧退 快速退款 免费包邮
            </text>
          </view>
        </view>
      </view>
      <view class="detail panel">
        <view class="title">
          <text class="sk-transparent sk-text-0-0000-831 sk-text">详情</text>
        </view>
        <view class="content">
          <view class="properties">
            <view class="item">
              <text class="label sk-transparent sk-text-25-0000-366 sk-text">品名</text>
              <text class="value sk-transparent sk-text-25-0000-21 sk-text">及美雅文邑白兰地</text>
            </view>
          </view>
        </view>
      </view>
    </scroll-view>
    <view class="toolbar" style="padding-bottom: 34px">
      <view class="icons">
        <button class="icons-button sk-transparent sk-button sk-pseudo sk-pseudo-circle">
          <text class="icon-heart sk-pseudo sk-pseudo-circle"></text>收藏
        </button>
        <button
          class="icons-button sk-transparent sk-button sk-pseudo sk-pseudo-circle"
          open-type="contact"
        >
          <text class="icon-handset sk-pseudo sk-pseudo-circle"></text>客服
        </button>
        <navigator class="icons-button sk-transparent" open-type="switchTab">
          <text class="icon-cart sk-pseudo sk-pseudo-circle"></text>购物车
        </navigator>
      </view>
      <view class="buttons">
        <view
          class="addcart sk-transparent sk-text-31-9444-424 sk-text"
          style="background-position-x: 50%"
        >
          加入购物车
        </view>
        <view
          class="buynow sk-transparent sk-text-31-9444-179 sk-text"
          style="background-position-x: 50%"
        >
          立即购买
        </view>
      </view>
    </view>
  </view>
</template>
<style>
.sk-transparent {
  color: transparent !important;
}

.sk-opacity {
  opacity: 0 !important;
}

.sk-text-14-2857-992 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 78.4rpx;
  position: relative !important;
}

.sk-text {
  background-origin: content-box !important;
  background-clip: content-box !important;
  background-color: transparent !important;
  color: transparent !important;
  background-repeat: repeat-y !important;
}

.sk-text-14-2857-232 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 44.8rpx;
  position: relative !important;
}

.sk-text-0-0000-617 {
  background-image: linear-gradient(
    transparent 0%,
    #eeeeee 0%,
    #eeeeee 100%,
    transparent 0%
  ) !important;
  background-size: 100% 24rpx;
  position: relative !important;
}

.sk-text-14-2857-550 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-14-2857-731 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-14-2857-638 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-14-2857-262 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-14-2857-919 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-14-2857-759 {
  background-image: linear-gradient(
    transparent 14.2857%,
    #eeeeee 0%,
    #eeeeee 85.7143%,
    transparent 0%
  ) !important;
  background-size: 100% 36.4rpx;
  position: relative !important;
}

.sk-text-0-0000-831 {
  background-image: linear-gradient(
    transparent 0%,
    #eeeeee 0%,
    #eeeeee 100%,
    transparent 0%
  ) !important;
  background-size: 100% 28rpx;
  position: relative !important;
}

.sk-text-25-0000-366 {
  background-image: linear-gradient(
    transparent 25%,
    #eeeeee 0%,
    #eeeeee 75%,
    transparent 0%
  ) !important;
  background-size: 100% 52rpx;
  position: relative !important;
}

.sk-text-25-0000-21 {
  background-image: linear-gradient(
    transparent 25%,
    #eeeeee 0%,
    #eeeeee 75%,
    transparent 0%
  ) !important;
  background-size: 100% 52rpx;
  position: relative !important;
}

.sk-text-31-9444-424 {
  background-image: linear-gradient(
    transparent 31.9444%,
    #eeeeee 0%,
    #eeeeee 68.0556%,
    transparent 0%
  ) !important;
  background-size: 100% 72rpx;
  position: relative !important;
}

.sk-text-31-9444-179 {
  background-image: linear-gradient(
    transparent 31.9444%,
    #eeeeee 0%,
    #eeeeee 68.0556%,
    transparent 0%
  ) !important;
  background-size: 100% 72rpx;
  position: relative !important;
}

.sk-button {
  color: #efefef !important;
  background: #efefef !important;
  border: none !important;
  box-shadow: none !important;
}

.sk-image {
  background: #efefef !important;
}

.sk-pseudo::before,
.sk-pseudo::after {
  background: #efefef !important;
  background-image: none !important;
  color: transparent !important;
  border-color: transparent !important;
}

.sk-pseudo-rect::before,
.sk-pseudo-rect::after {
  border-radius: 0 !important;
}

.sk-pseudo-circle::before,
.sk-pseudo-circle::after {
  border-radius: 50% !important;
}

.sk-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: transparent;
}
</style>
