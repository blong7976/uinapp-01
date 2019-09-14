<template>
	<view class="content">
		<view class="uni-padding-wrap">
            <view class="page-section swiper">
				<image src="../../../static/img/ip.png" mode="" class="Ip"></image>
                <view class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
                        <swiper-item>
                            <view class="swiper-item">
								<image src="../../../static/img/banner1.png" mode="" class="img"></image>
							</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item">
								<image src="../../../static/img/banner1.png" mode="" class="img"></image>
							</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item">
								<image src="../../../static/img/banner1.png" mode="" class="img"></image>
							</view>
                        </swiper-item>
                    </swiper>
                </view>
            </view>
			
			<view class="page-section tabView">
				<view class="tabNav">
					<view :class="isActive==1?'tabs_item is-active':'tabs_item'" @click="tabSelect(1)">人脉加粉</view>
					<view :class="isActive==2?'tabs_item is-active':'tabs_item'" @click="tabSelect(2)">转发点赞</view>
					<view :class="isActive==3?'tabs_item is-active':'tabs_item'" @click="tabSelect(3)">群发消息</view>
				</view>
				<view class="tabs_content">
					<view :class="isActive==1?'tabs-tab-pane is-fadeIn':'tabs-tab-pane'">
						<view class="ul">
							<view class="li" v-for="(item,index) in uli1" :key="index">
								<image :src="item.icon" mode="aspectFit" class="icon"></image>
								<view class="name">{{item.name}}</view>
								<view class="des">{{item.des}}</view>
							</view>
						</view>
					</view>
					<view :class="isActive==2?'tabs-tab-pane is-fadeIn':'tabs-tab-pane'">
						<view class="ul">
							<view class="li" v-for="(item,index) in uli2" :key="index">
								<image :src="item.icon" mode="aspectFit" class="icon"></image>
								<view class="name">{{item.name}}</view>
								<view class="des">{{item.des}}</view>
							</view>
						</view>
					</view>
					<view :class="isActive==3?'tabs-tab-pane is-fadeIn':'tabs-tab-pane'">
						<view class="ul">
							<view class="li" v-for="(item,index) in uli3" :key="index">
								<image :src="item.icon" mode="aspectFit" class="icon"></image>
								<view class="name">{{item.name}}</view>
								<view class="des">{{item.des}}</view>
							</view>
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
            duration: 500,
			isActive:1,
			// 人脉加粉
			uli1:[
				{
					icon:'../../../static/img/index-icon1.png',
					name:'通信录加粉',
					des:'自动添加微信推荐的手机联系人',
					url:''
				},
				{
					icon:'../../../static/img/index-icon2.png',
					name:'群聊加粉',
					des:'高端圈客户，全自动添加微信群成员',
					url:''
				},
				{
					icon:'../../../static/img/index-icon3.png',
					name:'搜索加粉',
					des:'精准活粉丝，全自动搜索手机号添加',
					url:''
				},
				{
					icon:'../../../static/img/index-icon4.png',
					name:'附近加粉',
					des:'同城客户,全自动添加附近的人',
					url:''
				},
				{
					icon:'../../../static/img/index-icon5.png',
					name:'扫描加粉',
					des:'幼稚科员，全自动扫描二维码添加',
					url:''
				},
				{
					icon:'../../../static/img/index-icon6.png',
					name:'扫描加群',
					des:'海量活跃微信群全自动扫描添加',
					url:''
				}
			],
			uli2:[
				{
					icon:'../../../static/img/index-icon7.png',
					name:'自动转发',
					des:'一键转发聊天窗口朋友圈图片或视频',
					url:''
				},
				{
					icon:'../../../static/img/index-icon8.png',
					name:'自动点赞',
					des:'自动在朋友圈批量点赞',
					url:''
				},
				{
					icon:'../../../static/img/index-icon9.png',
					name:'自动评论',
					des:'自动在朋友圈批量评论',
					url:''
				}
			],			
			uli3:[
				{
					icon:'../../../static/img/index-icon10.png',
					name:'群发群',
					des:'一键发送消息到多个 微信群',
					url:''
				},
				{
					icon:'../../../static/img/index-icon11.png',
					name:'群发好友',
					des:'一键发送图片、文字消息 给多个好友',
					url:''
				},
				{
					icon:'../../../static/img/index-icon12.png',
					name:'群发名片',
					des:'一键发送好友名片到 多 个微信群',
					url:''
				},
				{
					icon:'../../../static/img/index-icon13.png',
					name:'群发收藏到群',
					des:'一键发送收藏到多个 微信群',
					url:''
				}
			],
		};
	},
	onLoad() {},
	methods: {
		navigatorto(v){
			console.log(v)
		},
		tabSelect(ele){
			this.isActive=ele
		}
	},
	onPullDownRefresh() {
		setTimeout(function () {
            uni.stopPullDownRefresh();
        }, 1000);
	},

};
</script>

<style lang="scss" scoped>
	/deep/ uni-page-wrapper{
		overflow-y: auto;
	}
.content {
	.swiper{
		width: 100%;
		height: 804upx;
		background-color:#FFFFFF;
		position:relative;
		.Ip{
			position: absolute;
			top: 48upx;
			left: 50upx;
			z-index: 999;
			width: 404upx;
			height: 62upx;
		}
		.swiper-item,
		.img{
			width: 100%;
			height: 100%;
		}
		/deep/ uni-swiper .uni-swiper-dots-horizontal{
			right: 0 !important;
			bottom: 80upx !important;
			left: auto;
			/deep/ .uni-swiper-dot{
				background: #fff;
				opacity: .6;
			}
			/deep/ .uni-swiper-dot-active{
				opacity: 1;
				width: 30upx;
				border-radius: 8upx;
			}
		}
	}

	.tabView{
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		top: 751upx;
		background: #FFFFFF;
		border-top-left-radius: 24upx;
		border-top-right-radius: 24upx;
		box-sizing: border-box;
		padding:15upx 30upx;
		.tabNav{
			display: flex;
			align-items: center;
			justify-content: space-between;	
			.tabs_item{
				font-size: 36upx;
				color: #808080;
				position: relative;
				margin:20upx;
				cursor: pointer;
			}
			.tabs_item.is-active{
				color: #333333;
				font-weight: bold;
			}
			.tabs_item.is-active:after{
				content:"";
				width: 50upx;
				height: 8upx;
				background-color: #333;
				border-radius: 4upx;
				position: absolute;
				bottom: -20upx;
				left: 50%;
				transform: translateX(-50%);
			}
		}
		
		.tabs_content{
			box-sizing: border-box;
			overflow: hidden;
			.tabs-tab-pane{
				display: none;
				overflow: hidden;
				padding-top:30upx;
				padding-bottom:30upx;
				.ul>.li{
					width: 33.3333%;
					padding: 20upx 14upx;
					box-sizing: border-box;
					overflow: hidden;
					text-align: center;
					float: left;
					.icon{
						max-width: 70upx;
						max-height: 60upx;
					}
					.name{
						margin-top: 18upx;
						font-size: 24upx;
						color: #333333;
					}
					.des{
						font-size: 14upx;
						color: #808080;
						overflow: hidden;
						text-overflow: ellipsis;
						display: -webkit-box;
						-webkit-line-clamp: 2; 
						-webkit-box-orient: vertical;
					}
				}
			}
			.tabs-tab-pane.is-fadeIn{
				display: block;
			}
		}
		
	}
}
</style>
