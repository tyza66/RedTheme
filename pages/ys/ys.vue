<template>
	<view>
		<view class="top"></view>
			<view class="shipin">
				<view class="one" v-for="(item,i) in sp" @click="go(item[0])">
					<view class="p1"><image :src="item[1]" mode="widthFix"></image></view>
					<view class="p2">
						<view class="title"><p>{{item[2]}}</p></view>
						<view class="xm">
								<view class="s1">{{item[3]}}</view>
								<view class="s2" @click="zan(i)"><image class="zan" :src="item[5]"></image>{{item[4]}}</view>
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
				sp:[[5,"https://s2.loli.net/2022/04/09/kqX8cEi5tH1jWSZ.png","《长津湖》","红影小编","8854","../../static/icons/ai.png"],
				[1,"https://s2.loli.net/2022/04/09/HV5QxL9MscYPzJW.png","《建军大业》","红影小编","1222","../../static/icons/ai.png"],
				[2,"https://s2.loli.net/2022/04/09/WVio2nPBOzGkvpw.png","《我和我的父辈》四位导演故事水准排名：章>吴>徐>沈","红影大编","1234","../../static/icons/ai.png"],
				[3,"https://s2.loli.net/2022/04/09/epDrvJbP4o62xkt.png","2009年《建国大业》 陈坤蒋经国cut","红影老编","3556","../../static/icons/ai.png"],
				[4,"https://s2.loli.net/2022/04/09/5xhWTtjopX3VQDm.png","《建党伟业》","爱心小编","6667","../../static/icons/ai.png"],
				[6,"https://s2.loli.net/2022/04/09/8WAhspGE2UFCNdm.png","《长津湖之水门桥》","红影小编","5674","../../static/icons/ai.png"]
				]
			}
		},
		methods: {
			zan(i){
				if(this.sp[i][5] == "../../static/icons/ai2.png")
				{
					this.sp[i][5] = "../../static/icons/ai.png";
					this.sp[i][4] = parseInt(this.sp[i][4]) - 1;
				}
				else
				{
					this.sp[i][5] = "../../static/icons/ai2.png";
					this.sp[i][4] = parseInt(this.sp[i][4]) + 1;
				}
				this.$forceUpdate();
			},
			go(i){
				uni.navigateTo({
					url:"../sp/sp?num=" + i
				})
			}
		}
	}
</script>

<style>
	.top {
			height: var(--status-bar-height);
			width: 100%;
			background-color: #FFFFFF;
		}
		
		.one{
			float: left;
			width: 375rpx;
			height: 600rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			background: #F8F8F8;
		}
		.p1{
			position: relative;
			height: 450rpx;
			width: 350rpx;
			background: #00000f;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.p1 image{
			width: 350rpx;
		}
		.p2{
			height: 130rpx;
			width: 350rpx;
			background: #FFFFFF;
			border-bottom-left-radius: 25rpx;
			border-bottom-right-radius: 25rpx;
		}
		.p2 .title{
			width: 100%;
			height: 65rpx;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.p2 .title p{
			font-weight: 650;
			width: 350rpx;
			overflow: hidden;
			text-overflow:ellipsis;
			white-space: nowrap;
		}
		.xm{
			width: 100%;
			height: 65rpx;
		}
		.s1{
			float: left;
			height: 65rpx;
			width: 200rpx;
			margin-left: 20rpx;
			display: flex;
			flex-direction: row;
			justify-content: left;
			align-items: center;
		}
		.s2{
			float: left;
			height: 65rpx;
			width: 130rpx;
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;
		}
		.zan{
			width: 30rpx;
			height: 30rpx;
		}
		.bff{
			position: absolute;
			left: 250rpx;
			top: 0;
			width: 100rpx !important;
		}
	</style>
