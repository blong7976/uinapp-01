<template>
	<view class="content">
		<view class="uni-padding-wrap">
            <view class="page-section swiper">
                <view class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
                        <swiper-item>
                            <view class="swiper-item uni-bg-red">A</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-green">B</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-blue">C</view>
                        </swiper-item>
                    </swiper>
                </view>
            </view>
			
			<view class="page-section mt section1">
				<view class="heade">人脉加粉</view>
				<view class="list">
					<view class="item" v-for="(v,index) in 6" :key="index" @click="navigatorto(index)">
						<image src="../../../static/img/release.png" mode="" class="icon"></image>
						<view class="title">
							通信录加粉
						</view>
						<view class="describe">
							自动添加微信推荐的手机联系人
						</view>
					</view>
				</view>
			</view>
			
			<view class="page-section mt section1">
				<view class="heade">转发点赞</view>
				<view class="list">
					<view class="item" v-for="(v,index) in 3" :key="index" @click="navigatorto(index)">
						<image src="../../../static/img/release.png" mode="" class="icon"></image>
						<view class="title">
							通信录加粉
						</view>
						<view class="describe">
							自动添加微信推荐的手机联系人
						</view>
					</view>
				</view>
			</view>
			
			<view class="page-section mt section1">
				<view class="heade">群发消息</view>
				<view class="list">
					<view class="item" v-for="(v,index) in 3" :key="index" @click="navigatorto(index)">
						<image src="../../../static/img/release.png" mode="" class="icon"></image>
						<view class="title">
							通信录加粉
						</view>
						<view class="describe">
							自动添加微信推荐的手机联系人
						</view>
					</view>
				</view>
			</view>
        </view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			background: ['color1', 'color2', 'color3'],
            indicatorDots: true,
            autoplay: true,
            interval: 2000,
            duration: 500
		};
	},
	onLoad() {},
	methods: {
		navigatorto(v){
			console.log(v)
		},
	},
	onPullDownRefresh() {
		setTimeout(function () {
            uni.stopPullDownRefresh();
        }, 1000);
	},

};
</script>

<style lang="scss" scoped>
page{background-color: #f5f5f5;}
.content {
	.swiper{
		background-color: #007AFF;
		text-align: center;	
	}
	.mt{
		margin-top: 20upx;
		padding: 20upx;
		box-sizing: border-box;
	}
	.section1{
		background-color: #fff;
		.heade{
			font-size: 32upx;
			position: relative;
			padding-left: 20upx;
		}
		.heade::after{
			content: "";
			width: 4upx;
			height: 32upx;
			background-color: #007AFF;
			position: absolute;
			left: 0;
			top: 50%;
			transform: translateY(-50%);
		}
		.list{
			box-sizing: border-box;
			overflow: hidden;
			.item{
				width: 33.3333%;
				float: left;
				text-align: center;
				box-sizing: border-box;
				padding:20upx;
				.icon{
					width: 60upx;
					height: 60upx;
					margin: 20upx 0;
				}
				.title{
					font-size: 28upx;
					color: #333;
				}
				.describe{
					font-size: 20upx;
					color: #999;
				}
			}
		}
	}
}
</style>
