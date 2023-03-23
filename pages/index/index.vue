<template>
	<view class="content">
		<view class="header">
			<image src="@/static/banner.jpeg" mode="aspectFill"></image>
		</view>
		
		<view class="feeds">
			<view class="title">
				<text class="tt">已发布</text>
				<text class="dd">{{number_feed_box}}个盒子，{{number_feed_bag}}个冰袋</text>
				<navigator url="/pages/create/create">+发布信息</navigator>
			</view>
			<block v-for="feed in feeds">
				<view class="feed">
					<image :src="feed.img" mode="aspectFill"></image>
					<view>
						<text class="status">{{feed.status}}</text>
						<text class="time">发布时间：{{feed.time}}</text>
					</view>
					<view class="score" v-if="feed.score !== 0">+{{feed.score}}</view>
					<view class="score" v-else><text class="txt-gray">待评估</text></view>
					
				</view>
			</block>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				number_feed_box : 128,
				number_feed_bag : 88,
				feeds : [
					{
						status : "待回收",
						time : "2021/12/21 18:23:21",
						score : 0,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/11/21 18:23:21",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/10/21 15:22:11",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/11/21 18:23:21",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/10/21 15:22:11",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/11/21 18:23:21",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/10/21 15:22:11",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/11/21 18:23:21",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/10/21 15:22:11",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/11/21 18:23:21",
						score : 11,
						img : "/static/box.png"
					},
					{
						status : "已回收",
						time : "2021/10/21 15:22:11",
						score : 11,
						img : "/static/box.png"
					}
				]
			}
		},
		onLoad() {
			this.init_feeds();
		},
		methods: {
			init_feeds : function(){
				console.log(1111)
				const { Client } = require("@notionhq/client");
				// Initializing a client
				const notion = new Client({
				  auth: "secret_BSWF2WlFz2YVcFrr2B9IyacELPconZ6K5rweTh3wdWO",
				});
				
				(async () => {
				  const databaseId = 'c68fe24a8c034e0ca09561ccf9dae727';
				  const response = await notion.databases.query({
				    database_id: databaseId
				  });
				  console.log(response);
				  console.log(222);
				  
				})();
			}
		}
	}
	
	
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-color: $uni-bg-color;
	}

	.header {
		display:flex;
		width:100%;
		justify-content: center;
		border-bottom: 1px solid $uni-border-color;
	}
	.header image {width:100%}
	
	.feeds {margin-top:-45rpx;position: relative;width:100%}
	.title {padding:0 20rpx 20rpx;font-size: 20rpx;height:28rpx;line-height:28rpx}
	.title .tt {float: left;font-size:28rpx;padding-right:15rpx}
	.title navigator { float: right;}
	
	.feed {padding:20rpx 20rpx 0 20rpx;display: flex;position:relative}
	.feed image {margin-right:20rpx;width:80rpx;height:80rpx}
	.feed .status {display:block;margin:10rpx 0;font-weight:bold;}
	.feed .score {position: absolute;width:80rpx;height:80rpx;line-height:80rpx;text-align:center;right:0}
	.feed .txt-gray {color: $uni-text-color-grey;}
</style>
