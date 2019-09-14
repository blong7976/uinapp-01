<template>
	<view class="content">
		<view class="tabber">
			<view :class="index==0?'item active':'item'" @click="tabchange(0)">微信号</view>
			<view :class="index==1?'item active':'item'" @click="tabchange(1)">微信群</view>
		</view>
		<view class="list">
			<view class="item" v-for="(v,index) in number" :key="index">
				<view class="body">
					<image src="../../../static/img/mv.png" mode="" class="icon"></image>
					<view class="name max"> Alexander Klaws </view>
					<view class="describe max">愿我们终有一番作为，感动无数</view>
					<button type="primary" plain="true" size="mini" class="btn">查看详情</button>
				</view>
			</view>
		</view>
		<view class="Addbtn">
			<image src="../../../static/img/addBtn.png" mode="aspectFit" class="img"></image>
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
	.content {
		padding:10upx 40upx 40upx;
		box-sizing:border-box;
		.tabber{
			position: relative;
			height:88upx;
			box-sizing: border-box;
			z-index:99;
			.item{
				font-size: 36upx;
				flex: 1;
				text-align: center;
				line-height: 88upx;
				background-color: #fff;
				display: inline-block;
				position: relative;
				color: #b2b2b2;
				margin-right: 20upx;
			}
			.item.active{
				color: #333;
				font-size: 56upx;
				font-weight: bold;
			}
			.item.active:after{
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
		.list{
			overflow: hidden;
			box-sizing: border-box;
			margin-top:40upx;
			.item{
				width: 100%;
				overflow: hidden;
				box-sizing: border-box;
				padding: 20upx 0;
				border-bottom:1px solid #f2f2f2;
				position:relative;
				.body{
					background: #fff;
					.icon{
						width: 100upx;
						height: 100upx;
						float: left;
						border-radius: 50%;
						overflow: hidden;
						margin-right: 20upx;
					}
					.max{
						max-width: 378upx;
						text-overflow: ellipsis;
						white-space: nowrap;
						overflow: hidden;
					}
					.btn{
						font-size: 24upx;
						color: #0076ff;
						border: 1px solid #0076ff;
						position: absolute;
						right: 0;
						top: 50%;
						transform: translateY(-50%);
					}
					.name{
						font-size: 30upx;
						color: #333333;
						line-height: 48upx;
					}
					.describe{
						margin-top: 10upx;
						font-size: 24upx;
						color: #999999;
					}
				}
			}
		}
		
		.Addbtn{
			position: fixed;
			right: 40upx;
			bottom: 160upx;
			z-index:9999;
			.img{
				width: 113upx;
				height: 123upx;
			}
		}
	}
</style>
