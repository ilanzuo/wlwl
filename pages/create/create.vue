<template>
	<view class="content">
		<view class="form">
			<view>
				<text class="legend">数量</text>
				<input class="ipt" type="text"/>
			</view>
			<view>
				<text class="legend">照片</text>
				<view class="upload-handler">
					<image src="@/static/icon-camera.png"></image>
				</view>
			</view>
			<view>
				<view class="btn-geo">
					<text>{{geo_district}}</text>
					<image src="@/static/icon-right.png"></image>
				</view>
			</view>
			<view class="btn-submit"><button>提交</button></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				geo_district : "枫桥丽舍"
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.content {height:100%;background-color: $uni-bg-color;position: absolute;width: 100%;}
	.form {padding:20rpx}
	.form .legend {display:flex;margin:40rpx 0;font-size: 20rpx;font-weight: bold;}
	.form .ipt {width:80%;height: 120rpx;background-color:#fff ; text-align: center;}
	.upload-handler image {width:100rpx;height:100rpx}
	.btn-geo {margin-top:40rpx;padding-left:25rpx;height:30rpx;line-height:30rpx;font-weight:bold;color:$uni-text-color-grey;background:#F1F1F1 url("@/static/icon-location.png") 0 6rpx no-repeat;background-size: 14rpx 20rpx;}
	.btn-geo image {margin-left:10rpx;width:10rpx;height:17rpx;position:relative;top:4rpx}
	.btn-submit {position: fixed;bottom:10px;width:100%}
	.btn-submit button {padding:0}

</style>
