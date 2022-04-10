<template>
	<view>
		<view class="top"></view>
		<view class="tp">
			<image class="left" src="../../static/icons/ic.png">
			<view class="right">
				<view :class="xiao1" @click="touchA()"><p>视频</p><image src="../../static/icons/sp.png"></image></view>
				<view :class="xiao2" @click="touchB()"><p>图文</p><image src="../../static/icons/tp.png"></image></view>
			</view>
		</view>
		<view class="a" v-show="ab">
			<view class="have"></view>
			<view class="shipin">
				<view class="one" v-for="(item,i) in sp" @click="go(item[0])">
					<view class="p1"><image :src="item[1]" mode="widthFix"></image><image class="bff" src="../../static/icons/sp.png" mode="widthFix"></image></view>
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
		<view class="b" v-show="!ab">
			<view class="have"></view>
			<view class="tuwen">
				<view class="one1" v-for="(item,i) in tw"  @click="go(item[0])">
					<view class="p11"><image class="tup" :src="item[1]" mode="widthFix"></image></view>
					<view class="p2">
						<view class="title"><p>{{item[2]}}</p></view>
						<view class="xm">
								<view class="s1">{{item[3]}}</view>
								<view class="s2" @click="zan2(i)"><image class="zan" :src="item[5]"></image>{{item[4]}}</view>
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
				xiao1: "xiao-1",
				xiao2: "xiao",
				ab: true,
				sp:[[1,"https://s2.loli.net/2022/04/09/HV5QxL9MscYPzJW.png","《建军大业》","红影小编","1222","../../static/icons/ai.png"],
				[2,"https://s2.loli.net/2022/04/09/WVio2nPBOzGkvpw.png","《我和我的父辈》四位导演故事水准排名：章>吴>徐>沈","红影大编","1234","../../static/icons/ai.png"],
				[3,"https://s2.loli.net/2022/04/09/epDrvJbP4o62xkt.png","2009年《建国大业》 陈坤蒋经国cut","红影老编","3556","../../static/icons/ai.png"],
				[4,"https://s2.loli.net/2022/04/09/5xhWTtjopX3VQDm.png","《建党伟业》","爱心小编","6667","../../static/icons/ai.png"],
				[5,"https://s2.loli.net/2022/04/09/kqX8cEi5tH1jWSZ.png","《长津湖》","红影小编","8854","../../static/icons/ai.png"],
				[6,"https://s2.loli.net/2022/04/09/8WAhspGE2UFCNdm.png","《长津湖之水门桥》","红影小编","5674","../../static/icons/ai.png"]
				],
				tw:[[7,"https://s2.loli.net/2022/04/09/XfBNEj27CnSIUxs.png","百年风流人物 曾国藩","红影小编","1222","../../static/icons/ai.png"],
				[8,"https://s2.loli.net/2022/04/09/Q8ze3wYNUyGjL25.png","儒学复兴与当代启蒙","红影大编","1234","../../static/icons/ai.png"],
				[9,"https://s2.loli.net/2022/04/09/XnWYtsTZR7OhGJw.png","马克思主义基本概论","红影老编","3556","../../static/icons/ai.png"],
				[10,"https://s2.loli.net/2022/04/09/iE61wysLxPeMkuZ.png","戏曲鉴赏","爱心小编","6667","../../static/icons/ai.png"],
				[11,"https://s2.loli.net/2022/04/09/SyHeqk6YruamDP7.png","书法鉴赏","红影小编","8854","../../static/icons/ai.png"],
				[12,"https://s2.loli.net/2022/04/09/EW62xXDaGreLZlu.png","美术鉴赏","红影小编","5674","../../static/icons/ai.png"]
				]
			}
		},
		onLoad() {

		},
		methods: {
			touchA(){
				this.xiao1 = "xiao-1";
				this.xiao2 = "xiao";
				this.ab = true;
			},
			touchB(){
				this.xiao1 = "xiao";
				this.xiao2 = "xiao-1";
				this.ab = false;
			},
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
			zan2(i){
				if(this.tw[i][5] == "../../static/icons/ai2.png")
				{
					this.tw[i][5] = "../../static/icons/ai.png";
					this.tw[i][4] = parseInt(this.tw[i][4]) - 1;
				}
				else
				{
					this.tw[5] = "../../static/icons/ai2.png";
					this.tw[i][4] = parseInt(this.tw[i][4]) + 1;
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
	.tp{
		position: fixed;
		left: 0;
		top: var(--status-bar-height);
		width: 100%;
		height: 100rpx;
		box-shadow: 0px 2px 5px #888888;
		background: #FFFFFF;
		z-index: 999;
	}
	.left{
		float: left;
		width: 100rpx;
		height: 100rpx;
		margin-left: 20rpx;
	}
	.right{
		float: right;
		height: 100rpx;
		width: 300rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		margin-right: 200rpx;
	}
	.xiao{
		margin: 0 auto;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.xiao-1{
		margin: 0 auto;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		border-bottom: #000000 solid 1rpx;
	}
	.xiao p,.xiao-1 p{
		color: #000000;
		font-size: 40rpx;
	}
	.xiao image,.xiao-1 image{
		width: 45rpx;
		height: 45rpx;
	}
	.a{
		width: 100%;
	}
	.have{
		width: 100%;
		height: 100rpx;
	}
	.shipin,.tuwen{
		width: 100%;
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
	.one1{
		float: left;
		width: 375rpx;
		height: 350rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background: #F8F8F8;
	}
	.p11{
		position: relative;
		height: 200rpx;
		width: 350rpx;
		background: #00000f;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.tup{
		width: 350rpx;
	}
</style>
