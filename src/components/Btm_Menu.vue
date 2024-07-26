<template>
	<div class="footer-menu">
		<div class="relative" style="width: 100%;">
			<div class="social-media-container">
				<a href="https://t.me/kk8official" target="_blank" class="social-media-icon">
					<img src="/images/telegram_icon.webp" alt="Telegram">
				</a>
				<a href="https://www.facebook.com/um.kk8/" target="_blank" class="social-media-icon">
					<img src="/images/Facebook_icon.png" alt="Facebook">
				</a>
				<a href="https://api.whatsapp.com/send/?phone=601135220768&text&type=phone_number&app_absent=0"
					target="_blank" class="social-media-icon">
					<img src="/images/Whatsapp_icon.png" alt="WhatsApp">
				</a>
			</div>
			<div class="footer-content">
				<div class="d-f col">
					<a href="https://www.atascasinobet.com/" target="_blank">
						<img src="/images/M24_BtmB_Home_Img.png" alt="Image 1">
					</a>
				</div>
				<div class="d-f col">
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/M24_BtmB_History_Img.png" alt="Image 2">
					</a>
				</div>
				<div class="d-f col">
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/M24_BtmB_Promo_Img.png" alt="Image 3">
					</a>
				</div>
				<div class="d-f col">
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/M24_BtmB_Live_Chat_Img.png" alt="Image 4">
					</a>
				</div>
				<div class="d-f col">
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/M24_BtmB_Setting_Img.png" alt="Image 5">
					</a>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'FooterMenu'
};
</script>

<style scoped>
.footer-menu {
	display: flex;
	justify-content: space-between;
	position: fixed;
	bottom: 0;
	width: 100%;
	height: 55px;
	background-image: url('/public/images/Mamak24_Btm_Banner.jpg');
	background-size: 100% 100%;
}

.relative {
	position: relative;
	z-index: 1;
}

.social-media-container {
	display: flex;
	flex-direction: column;
	position: absolute;
	top: -120px;
	left: 30px;
}

@media screen and (max-width: 426px) {
	.social-media-container {
		top: -135px !important;
		left: 15px !important;
	}
}

.social-media-icon {
	margin-bottom: 5px;
}

.footer-content {
	display: flex;
	justify-content: space-around;
	align-items: center;
	height: 100%;
}

.d-f {
	display: flex;
	justify-content: center;
}

.col {
	flex: 1;
	text-align: center;
}

.col img {
	width: 60px;
	height: auto;
}

@media screen and (max-width: 321px) {
	.col img {
		width: 30px;
	}
}

.social-media-icon img {
	width: 40px;
}
</style>
