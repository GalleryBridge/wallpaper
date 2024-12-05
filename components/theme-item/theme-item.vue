<template>
	<view class="themeItem">
		<navigator url="#" class="box" v-if="!isMore">
			<image class="pic" src="../../common/image/swapper2.png" mode="aspectFill"></image>
			<view class="mask">美女明星</view>
			<view class="tap">3天前更新</view>
		</navigator>
		<navigator url="#" class="box more" v-else>
			<image class="pic" src="../../common/image/swapper2.png" mode="aspectFill"></image>
			<view class="mask">
				<uni-icons type="more-filled" size="34" color="#fff"></uni-icons>
				<text>更多</text>
			</view>
		</navigator>
	</view>
</template>

<script setup>
	defineProps({
		isMore:{
			type: Boolean,
			default: false
		}
	})
</script>

<style lang="scss" scoped>
.themeItem {
	.box {
		height: 340rpx;
		border-radius: 10rpx;
		overflow: hidden;
		position: relative;
		.pic {
			width: 100%;
			// height: 600%;
		}
		.mask {
			width: 100%;
			height: 80rpx;
			position: absolute;
			bottom: 0;
			lef: 0;
			background: rgba(0, 0, 0, 0.2);
			color: #fff;
			display: flex;
			align-items: center;
			justify-content: center;
			backdrop-filter: blur(20rpx);
			font-weight: 600;
			font-size: 30rpx
		}
		.tap {
			position: absolute;
			left: 0;
			top: 0rpx;
			background: rgba(250, 129, 90, 0.7);
			backdrop-filter: blur(20rpx);
			font-style: 22rpx;
			padding: 6px 10px;
			border-radius: 0 0 20rpx 0;
			transform: scale(0.8);
			transform-origin: left top;
		}
	}
	/* 既有box 又有more */
	.box.more {
		.mask {
			width: 100%;
			height: 100%;
			flex-direction: column;
		}
		.text {
			font-size: 28rpx;
		}
	}
}
</style>