<template>
	<div class="Top_Banner_Container" />
</template>

<script>
export default {
	name: 'TopBanner'
};
</script>

<style scoped>
@media screen and (max-width: 767px) {
	.Top_Banner_Container {
		height: 50px !important;
	}

	.TR_Img {
		max-width: 40px;
	}
}

.Top_Banner_Container {
	background-image: url('/public/images/TBanner_Img.jpg');
	position: relative;
	background-size: cover;
	background-position: 0 24%;
	background-repeat: no-repeat;
	width: 100%;
	height: 60px;
}

.TopBanner {
	width: 100%;
}

.TR_Img {
	position: absolute;
	top: 50%;
	right: 20px;
	transform: translateY(-50%);
	max-width: 60px;
}
</style>
