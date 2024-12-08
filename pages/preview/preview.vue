<template>
	<view class="preview">
		<swiper circular>
			<swiper-item v-for="item in 5">
				<image @click="maskChange" src="../../common/image/scroll.png" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		
		<view class="mask" v-if="maskState">
			<view class="goBack">
				
			</view>
			<view class="count">
				3/9
			</view>
			<view class="time">
				<uni-dateformat :date="new Date()" format="hh:mm"/>
			</view>
			<view class="date">
				<uni-dateformat :date="new Date()" format="MM月dd日"/>
			</view>
			<view class="footer">
				<view class="box" @click="clickInfo">
					<uni-icons type="info" size="23">
						<view class="text">
							信息
						</view>
					</uni-icons>
				</view>
				<view class="box">
					<uni-icons type="info" size="23">
						<view class="text">
							5分
						</view>
					</uni-icons>
				</view>
				<view class="box">
					<uni-icons type="info" size="23">
						<view class="text">
							下载
						</view>
					</uni-icons>
				</view>
			</view>
		</view>
		<uni-popup ref="infoPopup">
			<view class="infoPopup">
				<view class="popHeader">
					<view></view>
					<view class="title">
						壁纸信息
					</view>
					<view class="close">
						<uni-icons type="closeempty" size="18" color="#999"></uni-icons>
					</view>
				</view>
				<scroll-view scroll-y >
					<view class="content">
						<view class="row" v-for="item in 4">
							{{item}}
						</view>
					</view>
				</scroll-view>
			</view>
		</uni-popup>
	</view>
</template>

<script setup>
import { ref } from 'vue';

const maskState = ref(true)
const infoPopup= ref(null)
//	遮罩
const maskChange = () => {
	maskState.value = !maskState.value;
}
//	信息弹窗
const clickInfo = () =>{
	infoPopup.value.open(); 
}
</script>

<style lang="scss" scoped>
	.preview {
		width: 100%;
		height: 100vh;
		position: relative;
		swiper { 
			width: 100%;
			height: 100%;
			image {
				width: 100%;
				height: 100%;
			}
		}
		.mask {
			&>view {
				position: absolute;
				left: 0;
				right: 0;
				margin: auto;
				width: fit-content;
			}
			.goBack {
				
			}
			.count {
				top: 10vh;
				background: rgba(0, 0, 0, 0.3);
				font-size: 28rpx;
				color: #fff;
				border-radius: 40rpx;
				padding: 8rpx 28rpx;
				backdrop-filter: blur(10rpx);
			}
			.time {
				font-size: 140rpx;
				top: calc(10Vh + 80rpx);
				font-weight: 100;
				line-height: 1em;
				text-shadow: 0 2rpx rgba(0, 0, 0, 0.3);
			}
			.date {
				font-size: 34rpx;
				top: calc(10vh + 230rpx);
				text-shadow: 0 2rpx rgba(0, 0, 0, 0.3);
			}
			.footer {
				background: rgba(255, 255, 255, 0.8);
				bottom: 10vh;
				width: 65vw;
				height: 120rpx;
				border-radius: 120rpx;
				color: #000;
				display: flex;
				justify-content: space-around;
				align-items: center;
				box-shadow: 0 2rpx 0 rgba(0, 0, 0, 0.1);
				backdrop-filter: blur(20rpx);
				.box {
					display: flex;
					flex-direction: column;
					align-items: center;
					justify-content: center;
					padding: 2rpx 12rpx;
					.text {
						font-size: 26rpx;
						color: $text-font-color-2;
					}
				}
			}
		}
	}
</style>
