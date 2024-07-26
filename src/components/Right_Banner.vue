<template>
	<div class="Right_Banner_Container">
		<div class="RB_Imgs">
			<div class="login-register-container">
				<a href="https://www.atascasinobet.com/sign-up"><img src="/images/RB_Login_Btn_Img.png" alt=""></a>
				<a href="https://www.atascasinobet.com/sign-up"><img src="/images/RB_Register_Btn_Img.png" alt=""></a>
			</div>
			<div style="display: flex; margin-bottom: 23px">
				<div class="RB_Small_Text_Container">
					<div class="Baki">
						<p>Baki:</p>
						<p><strong>0.00</strong></p>
					</div>
					<p>Deposit Minimum: <strong>RM5.00</strong></p>
					<p>Withdraw Minimum: <strong>RM50.00</strong></p>
				</div>
				<div class="RB_Cash_Btn_Container">
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/RB_Deposit_Btn_Img.png" alt="">
					</a>
					<a href="https://www.atascasinobet.com/sign-up" target="_blank">
						<img src="/images/RB_Withdraw_Btn_Img.png" alt="">
					</a>
					<a href="https://www.atascasinobet.com/sign-up"><img src="/images/RB_Refresh_Btn_Img.png"
							alt=""></a>
				</div>
			</div>

			<div class="Tablet-Mobile-view">
				<img src="/images/LB_Img_2.jpg" alt="">
				<div class="button-grp">
					<a href="https://www.atascasinobet.com/sign-up"><img class="col-6" src="/images/M24_Share_btn.gif"
							alt=""></a>
					<a href="https://www.atascasinobet.com/sign-up"><img class="col-6"
							src="/images/M24_Downline_btn.png" alt=""></a>
					<a href="https://www.atascasinobet.com/sign-up"><img class="col-6" src="/images/M24_Copy_btn.png"
							alt=""></a>
					<a href="https://www.atascasinobet.com/sign-up"><img class="col-6" src="/images/M24_More_btn.png"
							alt=""></a>
				</div>
			</div>


			<div class="sport-betting-container">

			</div>

			<a href="https://www.atascasinobet.com/sign-up"><img src="/images/Atas-Post-Banner-(Eng).webp" alt=""
					style="margin-bottom: 16px;"></a>
			<a href="https://www.atascasinobet.com/sign-up"><img src="/images/check_in.webp" alt=""
					style="margin-bottom: 16px;"></a>
		</div>
	</div>
</template>


<script>
export default {
	name: 'RightBanner'
};
</script>

<style scoped>
.Right_Banner_Container {
	background: rgba(0, 0, 0, .3);
	padding: 10px 15px 30px 15px;
	height: 100%;
}


.RB_Imgs img {
	max-width: 100%;
}

.RB_Cash_Btn_Container {
	width: 50%;
	padding-left: 15px;
	text-align: right;
}

.RB_Cash_Btn_Container img {
	width: 130px;
}

.login-register-container {
	padding: 10px 0;
	display: flex;
}

.login-register-container img {
	padding: 0 5px;
}

.RB_Small_Text_Container {
	display: flex;
	flex-direction: column;
	width: 50%;
	white-space: nowrap;
	justify-content: space-around;
}

.RB_Small_Text_Container p {
	color: white;
	font-size: 13px;
	font-weight: 400;
	font-family: Lato, sans-serif;
	margin-bottom: 0;
}

.RB_Small_Text_Container strong {
	font-weight: bold !important;
}

.Baki {
	display: flex;
	flex-direction: column;
	margin-bottom: 7px;
}

.Baki p {
	margin: 5px 0;
}

.Baki strong {
	color: #4798d1;
	font-size: 19.5px;
}

.Tablet-Mobile-view {
	display: none;
}

@media screen and (max-width: 1000px) {
	.Tablet-Mobile-view {
		display: flex !important;
		flex-direction: column;
	}

	.RB_Cash_Btn_Container {
		display: flex;
		flex-direction: column;
		align-items: flex-end;
		justify-content: space-around;
	}

	.RB_Cash_Btn_Container img {
		width: 80%;
	}

	.RB_Small_Text_Container {
		justify-content: space-between;
	}

	.RB_Small_Text_Container p {
		font-size: 30px;
	}

	.Baki strong {
		font-size: 40px;
	}
}

@media screen and (max-width: 430px) {
	.RB_Small_Text_Container p {
		font-size: 14px;
	}

	.Baki strong {
		font-size: 20px;
	}
}

.button-grp {
	margin-top: -25%;
	display: flex;
	flex-wrap: wrap;
}

.button-grp img {
	width: 50%;
	padding: 0 5px;
	margin-bottom: 16px;
}

.sport-betting-container {
	background-image: url('/public/images/soccer-betting-img.jpg');
}
</style>