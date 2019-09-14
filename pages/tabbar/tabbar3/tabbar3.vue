<template>
	<view class="content">
		<image src="../../../static/img/me-bgImg.png" mode="" class="bgImg"></image>
		<view class="Header">
			个人中心
		</view>
		<view class="U_info">
			<view class="u-lt">
				<view>
					<image src="../../../static/img/icon_code.png" mode="aspectFit" class="icon"></image>
					<view class="name">激活码</view>
				</view>
			</view>
			<view class="u-rt">
				<view class="">
					<view class="code">
						WMMYTFS4PWZE2ZKKCMDNYQ
					</view>
					<view class="time">
						2019-10-11  17:58:17 到期
					</view>
				</view>
			</view>
		</view>
		<view class="ul">
			<view class="li" v-for="(item,index) in navs" :key="index">
				<image :src="item.icon" mode="aspectFit" class="icon"></image>
				{{item.name}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navs:[
					{
						name:'常用设置',
						icon:'../../../static/img/icon_setting.png',
						url:''
					},{
						name:'使用帮助',
						icon:'../../../static/img/icon_help.png',
						url:''
					},{
						name:'建议反馈',
						icon:'../../../static/img/icon_idea.png',
						url:''
					},
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.content {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: #F1F1F1;
		background-size:100% 640upx;
		box-sizing: border-box;
		padding: 44upx 40upx 128upx;
		.bgImg{
			position: absolute;
			top: 0;
			left: 0;
			right: 0;
			width: 100%;
			height: 640upx;
		}
		.Header{
			font-size: 56upx;
			color: #fff;
			position: relative;
			z-index: 99;
		}
		.U_info{
			width: 100%;
			margin-top: 347upx;
			box-sizing: border-box;
			height: 180upx;
			background: url(../../../static/img/yhj.png) no-repeat top;
			background-size: 100% 100%;
			position: relative;
			z-index: 99;
			padding-left:170upx;
			.u-lt{
				width: 170upx;
				height: 180upx;
				display: flex;
				align-items: center;
				text-align: center;
				justify-content: space-around;
				font-size:24upx;
				color:#333;
				position:absolute;
				left:0;
				.icon{
					display: block;
					width: 56upx;
					height: 56upx;
					margin: 0 auto 14upx;
				}
			}
			.u-rt{
				height: 180upx;
				box-sizing: border-box;
				display: flex;
				align-items: center;
				margin: 0 20upx;
				text-overflow: ellipsis;
				white-space: nowrap;
				overflow: hidden;
				word-wrap: break-word;
				.code{
					font-size: 30upx;
					color: #333333;
					text-overflow: ellipsis;
					white-space: nowrap;
					overflow: hidden;
					word-wrap:break-word;
				}
				.time{
					font-size: 24upx;
					color: #0076ff;
					background: #e5f1ff;
					display: inline-block;
					padding: 5upx 20upx;
					border-radius: 30upx;
				}
			}
		}
		.ul{
			margin-top: 30upx;
			background: #FFFFFF;
			border-radius: 20upx;
			padding: 20upx 30upx;
			.li{
				box-sizing: border-box;
				display: flex;
				height: 88upx;
				align-items: center;
				background:url(../../../static/img/icon_more.png) no-repeat right;
				background-size:16upx 28upx;
				font-size:30upx;
				color:#333333;
				cursor: pointer;
				margin-bottom:20upx;
				.icon{
					width: 40upx;
					height: 40upx;
					margin-right: 20upx;
				}
				
			}
			.li:last-child{margin-bottom: 0;}
		}
	}
</style>
