<template name="skeleton">
    <view class="sk-container">
        <view class="viewport">
            <view class="search">
                <view class="input">
                    <text
                        class="icon-search sk-transparent sk-text-14-2857-215 sk-text sk-pseudo sk-pseudo-circle">女靴</text>
                </view>
            </view>
            <view class="categories">
                <scroll-view :scroll-y="true" class="primary">
                    <view class="item active sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-88 sk-text">居家</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-609 sk-text">美食</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-496 sk-text">服饰</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-603 sk-text">母婴</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-163 sk-text">个护</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-704 sk-text">严选</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-305 sk-text">数码</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-646 sk-text">运动</text>
                    </view>
                    <view class="item sk-pseudo sk-pseudo-circle">
                        <text class="name sk-transparent sk-text-14-2857-453 sk-text">杂项</text>
                    </view>
                </scroll-view>
                <scroll-view :scroll-y="true" class="secondary">
                    <view is="components/XtxSwiper" class="banner">
                        <view class="carousel XtxSwiper--carousel">
                            <swiper :circular="true" :interval="3000" :current="0" :autoplay="false">
                                <swiper-item
                                    style="position: absolute; width: 100%; height: 100%; transform: translate(0%, 0px) translateZ(0px);">
                                    <navigator class="navigator XtxSwiper--navigator" hover-class="none">
                                        <image class="image XtxSwiper--image sk-image" mode="aspectFill"></image>
                                    </navigator>
                                </swiper-item>
                                <swiper-item
                                    style="position: absolute; width: 100%; height: 100%; transform: translate(100%, 0px) translateZ(0px);">
                                    <navigator class="navigator XtxSwiper--navigator" hover-class="none">
                                        <image class="image XtxSwiper--image sk-image" mode="aspectFill"></image>
                                    </navigator>
                                </swiper-item>
                            </swiper>
                            <view class="indicator XtxSwiper--indicator">
                                <text class="dot XtxSwiper--dot active XtxSwiper--active"></text>
                                <text class="dot XtxSwiper--dot"></text>
                                <text class="dot XtxSwiper--dot"></text>
                                <text class="dot XtxSwiper--dot"></text>
                                <text class="dot XtxSwiper--dot"></text>
                            </view>
                        </view>
                    </view>
                    <view class="panel">
                        <view class="title">
                            <text class="name sk-transparent sk-text-28-0000-851 sk-text">居家生活用品</text>
                            <navigator class="more sk-transparent sk-text-30-0000-854 sk-text sk-pseudo sk-pseudo-circle"
                                hover-class="none">全部</navigator>
                        </view>
                        <view class="section">
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-302 sk-text">梅乃宿梅酒720毫升</view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-998 sk-text">168.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-717 sk-text">法国年份雅文邑700毫升</view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-162 sk-text">1480.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-667 sk-text">多米尼加陈年朗姆酒700毫升</view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-411 sk-text">238.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-73 sk-text">全新升级，四川酸辣粉195克*6杯
                                </view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-961 sk-text">69.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-906 sk-text">川味牛肉辣椒酱190克</view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-526 sk-text">38.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                                <view class="name ellipsis sk-transparent sk-text-14-2857-540 sk-text">智利老牌名庄，梅洛干红750毫升
                                </view>
                                <view class="price">
                                    <text class="symbol sk-transparent sk-opacity">¥</text>
                                    <text class="number sk-transparent sk-text-14-2857-483 sk-text">98.00</text>
                                </view>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                            </navigator>
                            <navigator class="goods" hover-class="none">
                                <image class="image sk-image"></image>
                            </navigator>
                        </view>
                    </view>
                </scroll-view>
            </view>
        </view>
    </view>
</template>

<style>
.sk-transparent {
    color: transparent !important;
}

.sk-text-14-2857-215 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text {
    background-origin: content-box !important;
    background-clip: content-box !important;
    background-color: transparent !important;
    color: transparent !important;
    background-repeat: repeat-y !important;
}

.sk-text-14-2857-88 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-609 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-496 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-603 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-163 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-704 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-305 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-646 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-14-2857-453 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 36.0938rpx;
    position: relative !important;
}

.sk-text-28-0000-851 {
    background-image: linear-gradient(transparent 28.0000%, #EEEEEE 0%, #EEEEEE 72.0000%, transparent 0%) !important;
    background-size: 100% 58.5938rpx;
    position: relative !important;
}

.sk-text-30-0000-854 {
    background-image: linear-gradient(transparent 30.0000%, #EEEEEE 0%, #EEEEEE 70.0000%, transparent 0%) !important;
    background-size: 100% 58.5938rpx;
    position: relative !important;
}

.sk-text-14-2857-302 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-opacity {
    opacity: 0 !important;
}

.sk-text-14-2857-998 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-text-14-2857-717 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-text-14-2857-162 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-text-14-2857-667 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-text-14-2857-411 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-text-14-2857-73 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-text-14-2857-961 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-text-14-2857-906 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-text-14-2857-526 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-text-14-2857-540 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 29.5313rpx;
    position: relative !important;
}

.sk-text-14-2857-483 {
    background-image: linear-gradient(transparent 14.2857%, #EEEEEE 0%, #EEEEEE 85.7143%, transparent 0%) !important;
    background-size: 100% 32.8125rpx;
    position: relative !important;
}

.sk-image {
    background: #EFEFEF !important;
}

.sk-pseudo::before,
.sk-pseudo::after {
    background: #EFEFEF !important;
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
}</style>
