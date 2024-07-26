<template>
	<div style="padding-top: 10px; margin-bottom: 16px;" id="carouselExampleInterval" class="carousel slide"
		data-bs-ride="carousel">
		<div class="carousel-inner">
			<div class="carousel-item active" data-bs-interval="4000">
				<img width="100%" src="/images/LB_Slider_Img_1.jpg" class="d-block w-100" alt="slide1">
			</div>
			<div class="carousel-item" data-bs-interval="4000">
				<img width="100%" src="/images/LB_Slider_Img_2.jpg" class="d-block w-100" alt="slide2">
			</div>
			<div class="carousel-item" data-bs-interval="4000">
				<img width="100%" src="/images/LB_Slider_Img_3.jpg" class="d-block w-100" alt="slide3">
			</div>
		</div>
	</div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap';

export default {
	data() {
		return {
			currentIndex: 0,
		};
	},
};
</script>

<style>
.carousel-item img {
	height: 148px;
}
</style>
