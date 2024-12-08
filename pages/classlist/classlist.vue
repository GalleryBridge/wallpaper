<template>
	<view class="classlist">
		<view class="content">
			<navigator class="item" url="" v-for="item in 10">
				<image src="../../common/image/scroll.png" mode="aspectFill"></image>
			</navigator>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style>
	.content {
		display: grid;
		grid-template-columns: repeat(3,1fr);
		gap: 5rpx;
		padding: 5rpx;
		.item {
			height: 440rpx;
			image {
				width: 100%;
				height: 100%;
				display: block;
			}
		}
	}
	       
</style>
