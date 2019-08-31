<template>
	<view class="content">
		<view class="tabber">
			<view :class="index==0?'item active':'item'" @click="tabchange(0)">微信号</view>
			<view :class="index==1?'item active':'item'" @click="tabchange(1)">微信群</view>
		</view>
		<view class="list">
			<view class="item" v-for="(v,index) in number" :key="index">
				<view class="body">
					<image src="../../../static/logo.png" mode="" class="icon"></image>
					<view class="name">曾老师</view>
					<view class="describe">描述</view>
					<button type="primary" plain="true" size="mini">查看</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				index:0,
				number:6
			}
		},
		onLoad() {

		},
		methods: {
			tabchange(idx){
				this.index=idx
				if(idx==1){
					this.number=12
				}else{
					this.number=6
				}
			}
		},
		onPullDownRefresh() {
			let self = this
			setTimeout(function () {
		        uni.stopPullDownRefresh();
				self.index=0
				self.number=6
		    }, 1000);
		},
	}
</script>

<style lang="scss" scoped>
	page{background-color: #f5f5f5;}
	.content {
		.tabber{
			position: fixed;
			top: 80upx;
			display: flex;
			align-items: center;
			justify-content: space-between;
			width:100%;
			height:88upx;
			box-sizing: border-box;
			border-bottom:1px solid #f7f7f7;
			z-index:99;
			.item{
				font-size: 32upx;
				flex: 1;
				text-align: center;
				line-height: 88upx;
				background-color: #fff;
			}
			.item.active{
				color: #007AFF;
				font-weight: bold;
			}
		}
		.list{
			overflow: hidden;
			box-sizing: border-box;
			margin-top:88upx;
			.item{
				width: 33.3333%;
				overflow: hidden;
				box-sizing: border-box;
				padding: 20upx;
				float: left;
				.body{
					background: #fff;
					.icon{
						width: 100%;
						height: 220upx;
					}
				}
			}
		}
	}
</style>
