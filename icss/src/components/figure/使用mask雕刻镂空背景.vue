<template>
	<div class="bruce" data-title="使用mask雕刻镂空背景">
		<div class="mask-bg flex-ct-x">
			<div></div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
$mask-bg: "https://static.yangzw.vip/codepen/mask-bg.jpg";
$mask-text: "https://static.yangzw.vip/codepen/mask-text.jpg";
// $logo: "https://static.yangzw.vip/codepen/logo-netease.svg";
$logo: "../../assets/img/logo-netease.svg";
.bruce {
	padding: 0;
	height: 400px;
}
.mask-bg {
	overflow: hidden;
	position: relative;
	height: 100%;
	&::after {
		position: absolute;
		left: -20px;
		right: -20px;
		top: -20px;
		bottom: -20px;
		background: url($mask-bg) no-repeat center/cover;
		filter: blur(10px);
		content: "";
	}
	div {
		position: relative;
		z-index: 9;
		width: 600px;
		height: 300px;
		background: url($mask-text) left center/150% auto;
		mask: url($logo) center/cover;
		animation: move 10s infinite;
	}
}
@keyframes move {
	0% {
		background-position-x: 0;
	}
	50% {
		background-position-x: 100%;
	}
}
</style>