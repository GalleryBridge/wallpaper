<template>
	<view class="homeLayout">
		<view class="banner">
			<swiper indicator-dots indicator-color="rgba(255,255,255,0.5)" indicator-active-color="#fff" autoplay circular>
				<swiper-item v-for="item in 3">
					<image src="../../common/image/swapper1.png" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="notice">
			<view class="left">
				<uni-icons type="sound-filled" size="20" color="#28b389"></uni-icons>
				<text>公告</text>
			</view>
			<view class="center">
				<swiper vertical autoplay interval="1500" duration="300" circular>
					<swiper-item v-for="item in 4">文字内容</swiper-item>
				</swiper>
			</view>
			<view class="right">
				<uni-icons type="right" size="20" color="#333"></uni-icons>
			</view>
		</view>
		<view class="select">
			<common-title>
				<template #name>每日推荐</template>
				<template #custom>
					<view class="data">
						<uni-icons type="calendar" size="20" color="#28b389"></uni-icons>
						<view class="text">
							<uni-dateformat :date="Date.now()" format="dd号"></uni-dateformat>
						</view>
					</view>
				</template>
			</common-title>
			<view class="content">
				<scroll-view scroll-x>
					<view class="box" v-for="item in 8">
						<image src="../../common/image/scroll.png" mode="aspectFill"></image>
					</view>
				</scroll-view>
			</view>
		</view>
		<view class="theme">
			<common-title>
				<template #name>专题精选</template>
				<template #custom>
					<navigator url="" class="more">More+</navigator>
				</template>
			</common-title>
			
			<view class="content">
				<theme-item v-for="item in 8"></theme-item>
				<theme-item :isMore="true"></theme-item>
			</view>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
	.homeLayout {
		.banner {
			width: 750rpx;
			padding: 20rpx 0;
			swiper{
				width: 750rpx;
				&-item {
					width: 100%;
					height: 100%;
					padding: 0 20rpx;
					image {
						width: 100%;
						height: 100%;
						border-radius: 10rpx;
					}
				}
			}
		}
		.notice {
			width: 690rpx;
			height: 80rpx;
			background: #f9f9f9;
			margin: 0 auto;
			border-radius: 80rpx;
			display: flex;
			line-height: 80rpx;
			.left {
				width: 140rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				.text {
					color: #28b389;
					font-weight: 600;
					font-size: 28rpx
				}
			}
			.center {
				flex: 1;
				swiper {
					height: 100%;
					&-item {
						height: 100%;
						font-size: 30rpx;
						color: #666;
						overflow: hidden;
						white-space: nowrap;
						text-overflow: ellipsis;
					}
				}
			}
			.right {
				width: 70rpx;
				display: flex;
				align-items: center;
				justify-content: center;
			}
		}
		.select {
			padding-top: 50rpx;
			.content {
				width: 720rpx;
				margin-left: 30rpx;
				margin-top: 30rpx;
			}
			.data {
				color: #28b389;
				display: flex;
				align-items: center;
				.text {
					margin-left: 5rpx;
				}
			}
			scroll-view {
				white-space: nowrap;
				.box {
					width: 200rpx;
					height: 430rpx;
					display: inline-block;
					margin-right: 15rpx;
					image {
						width: 100%;
						height: 100%;
					}
				}
				.box:last-child {
					margin-right: 30rpx;
				}
			}
		}
		.theme{
			padding: 50rpx 0;
			.more {
				font-size: 32rpx;
				color: #888;
			}
			.content {
				margin-top: 30rpx;
				padding: 0 30rpx ;
				display: grid;
				gap: 15rpx;
				grid-template-columns: repeat(3,1fr);
			}
		}
	}
	
</style>
