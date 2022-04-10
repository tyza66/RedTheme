<template>
	<view>
		<view class="top"></view>
		<view class="iti"><h3>消息</h3></view>
		<view class="items">
			<view class="item">
				<image src="../../static/icons/pz.png"></image>
				<p>评赞</p>
			</view>
			<view class="item">
				<image src="../../static/icons/sc.png"></image>
				<p>收藏</p>
			</view>
			<view class="item">
				<image src="../../static/icons/pl.png"></image>
				<p>评论</p>
			</view>
		</view>
		<view :class="{am:i%2==0,am1:i%2!=0}" v-for="(item,i) in all">
					<image class="touxiang" :src="item[0]"></image>
					<p class="ming">{{item[1]}}</p>
					<p class="shi">{{item[2]}}</p>
					</image>
				</view>
			</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				all: [
									["https://img1.baidu.com/it/u=4216761644,15569246&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=500", "热血青年", "受到了爱国主义教育！"],
									["https://img1.baidu.com/it/u=583582599,306470958&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500", "我的三部曲", "厉害了！我的国~"],
									["https://img1.baidu.com/it/u=2601835228,2029613703&fm=253&fmt=auto&app=138&f=JPEG?w=400&h=400", "战狼侦察队", "我最喜欢的电影就是战狼系列"],
									["https://img0.baidu.com/it/u=178892670,2966992691&fm=253&fmt=auto&app=138&f=JPEG?w=400&h=400", "长津湖", "长津湖的故事始终让我印象深刻"],
									["https://img1.baidu.com/it/u=3983099563,2829714487&fm=253&fmt=auto&app=138&f=JPEG?w=400&h=400", "回顾1921", "给大家推荐了一些电影"]
								]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.top {
		height: var(--status-bar-height);
		width: 100%;
		background-color: #FFFFFF;
	}
	.items{
		width: 100%;
		height: 180rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.item{
		width: 180rpx;
		height: 180rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.item image{
		width: 100rpx;
		height: 100rpx;
	}
	.iti{
		width: 100%;
		height: 80rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.am {
			position: relative;
			width: 100%;
			height: 130rpx;
			background-color: #D0E0F3;
		}
		.am1 {
			position: relative;
			width: 100%;
			height: 130rpx;
			background-color: #FCE1C4;
		}
	.am .touxiang,
		.am1 .touxiang {
			position: absolute;
			width: 80rpx;
			height: 80rpx;
			top: 25rpx;
			left: 40rpx;
		}
		.am .dianhua,
		.am1 .dianhua {
			position: absolute;
			width: 40rpx;
			height: 40rpx;
			top: 25rpx;
			left: 680rpx;
		}
		.am .ming,
		.am1 .ming {
			position: absolute;
			height: 40rpx;
			top: 25rpx;
			left: 140rpx;
			font-family: "楷体";
			font-weight: 600rpx;
		}
		.am .shi,
		.am1 .shi {
			position: absolute;
			height: 40rpx;
			color: #7A6A57;
			top: 65rpx;
			left: 140rpx;
			font-family: "楷体";
			font-weight: 600rpx;
			font-size: 30rpx;
		}
</style>
