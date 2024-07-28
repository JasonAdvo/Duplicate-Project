<template>
	<div>
		<PopUpCard />
	</div>

	<div>
		<TopBanner />
	</div>

	<div class="running-sentence-container">
		<div class="running-sentence">
			{{ sentence }}
		</div>
	</div>

	<div class="main-content">
		<div class="LeftBanner col-sm-12 col-md-12 col-lg-3">
			<LeftBanner />
		</div>
		<!-- Middle Blank Column -->

		<div class="Middle_Banner_Container col-sm-12 col-md-12 col-lg-6">
			<div class="Middle_Inner_Container">
				<div class="site-tabs">
					<div v-for="(image, index) in images" :key="index" :id="'image-container-' + index"
						:class="['image-container', { selected: selectedIndex === index }]"
						@click="selectImage(index); handleRedirect(index)">
						<img :src="selectedIndex === index ? image.selected : image.notSelected"
							:alt="'Image ' + (index + 1)">
					</div>
				</div>

				<div class="MB_Img_Gallery">
					<div class="MB_Img" id="MB_Img">
						<div class="image-grid-container">
							<div class="image-wrapper" v-for="n in 53" :key="n">
								<img :src="`/images/MB_${n}_Img.jpg`" alt="Image" @click="redirectToSignUp">
								<button @click="redirectToSignUp">
									<p>{{ $t('message.Play') }}</p>
								</button>
							</div>
						</div>
					</div>
				</div>

				<div class="footer-content">
					<h2>
						Learn more about our big partner:
					</h2>
					<p>
						<a href="https://www.atascasinobet.com/">Atas Top Online Gaming Platform</a> | offers free
						credit to new players, allowing you
						to start your
						gaming journey with extra advantages. As a trusted online gaming platform in Malaysia, we
						provide a secure and reliable environment for all your gaming needs. Enjoy a wide range of games
						with confidence, knowing you’re playing on a platform dedicated to fairness, security, and
						top-notch customer service.
					</p>
					<p>
						<a href="https://www.ataskasino.com/">Atas Casino</a> | H5 3.0 web version | Discover Malaysia's
						premier gambling destination at Atas
						Casino, featuring a wide array of games such as live casino, slots, and sports betting. Known
						for its top-notch security, vast game variety, and excellent customer service, Atas Kasino
						ensures an outstanding gaming experience for all players.
					</p>

				</div>
			</div>
		</div>

		<!-- Right Banner Column -->
		<div class="RightBanner col-sm-12 col-md-12 col-lg-3">
			<RightBanner />
		</div>

	</div>
</template>

<script>
import { useI18n } from 'vue-i18n'; // Add this import
import LeftBanner from '/src/components/Left_Banner.vue';
import RightBanner from '/src/components/Right_Banner.vue';
import TopBanner from '/src/components/Top_Banner.vue';
import PopUpCard from '@/components/PopUpCard.vue';

export default {
	components: {
		LeftBanner,
		RightBanner,
		TopBanner,
		PopUpCard,
	},
	data() {
		return {
			selectedItem: 0,
			sentence: `MAMAK24 Official : Asia's Most Trusted and Reliable Gambling Platform  	Experience the top gambling destination in Malaysia, offering an extensive range of games including live casino, slots, and sportsbooks.MAMAK24 stands out with its exceptional security standards, extensive game selection, and highly responsive customer support. Join us today to enjoy generous welcome and promotional bonuses.Login to your account and immerse yourself in your favorite games for a smooth and rewarding gaming experience.`,
			selectedIndex: 0,
			images: [
				{ notSelected: '/images/AP_NotS.webp', selected: '/images/AP_S.webp' },
				{ notSelected: '/images/JILI_NotS.webp', selected: '/images/JILI_S.webp' },
				{ notSelected: '/images/RICH_NotS.webp', selected: '/images/RICH_S.webp' },
				{ notSelected: '/images/Bongo_NotS.webp', selected: '/images/Bongo_S.webp' },
				{ notSelected: '/images/Pragmatic_NotS.webp', selected: '/images/Pragmatic_S.webp' },
				{ notSelected: '/images/Playtech_NotS.webp', selected: '/images/Playtech_S.webp' },
				{ notSelected: '/images/AceWin_NotS.webp', selected: '/images/AceWin_S.webp' },
				{ notSelected: '/images/JDB_NotS.webp', selected: '/images/JDB_S.webp' },
				{ notSelected: '/images/Dragoon_NotS.webp', selected: '/images/Dragoon_S.webp' },
				{ notSelected: '/images/Rich88_NotS.webp', selected: '/images/Rich88_S.webp' },
				{ notSelected: '/images/Bigpot_NotS.webp', selected: '/images/Bigpot_S.webp' },
				{ notSelected: '/images/Slot_NotS.webp', selected: '/images/Slot_S.webp' },
				{ notSelected: '/images/Live_NotS.webp', selected: '/images/Live_S.webp' },
				{ notSelected: '/images/Sport_NotS.webp', selected: '/images/Sport_S.webp' },
				{ notSelected: '/images/Other_NotS.webp', selected: '/images/Other_S.webp' },
			],
		};
	},
	setup() {
		const { locale } = useI18n();
		const changeLanguage = (lang) => {
			locale.value = lang;
		};
		return {
			changeLanguage
		};
	},
	methods: {
		selectItem(event, index) {
			this.selectedItem = index;
			const clickedElementId = event.target.id;
			this.scrollToGame(clickedElementId);

			// Remove the active class from all items (assuming you have a way to select them)
			const items = document.querySelectorAll('.Top_Btn'); // Replace '.item' with your actual item selector
			items.forEach(item => {
				item.classList.remove('active');
			});

			// Add the active class to the clicked item
			event.target.classList.add('active');
		},
		scrollToGame(elementId) {
			let sectionId = '';
			if (elementId === 'Slot-Game') {
				sectionId = 'MB_Img';
			} else {
				sectionId = 'Game';
			}

			const sectionElement = document.getElementById(sectionId);
			if (sectionElement) {
				sectionElement.scrollIntoView({ behavior: 'smooth', block: 'start' });
			}
		},
		selectImage(index) {
			this.selectedIndex = index;
		},
		handleRedirect(index) {
			if (index === 0) {
				this.scrollToElement('.MB_Img_Gallery');
			} else {
				this.scrollToElement('.footer-content');
			}
		},
		scrollToElement(selector) {
			const element = document.querySelector(selector);
			if (element) {
				element.scrollIntoView({ behavior: 'smooth' });
			} else {
				console.error(`Element with selector ${selector} not found`);
			}
		},
		redirectToSignUp() {
			window.location.href = "https://www.atascasinobet.com/sign-up";
		}
	}
}
</script>

<style scoped>
@media screen and (max-width: 1000px) {
	.Mobile_Middle_Banner {
		display: flex !important;
		flex-direction: column;
		order: 1;
	}

	.Middle_Banner_Container {
		order: 2;
	}

	.main-content {
		flex-direction: column;
	}

	.MM_Small_Text_Container p {
		font-size: 18px !important;
		color: rgb(2, 47, 138);
	}
}

@media screen and (max-width: 431px) {
	.MM_Small_Text_Container p {
		font-size: 16px !important;
	}
}

.main-content {
	display: flex;
	width: 100%;
	background-image: url('/public/images/Bg_img.png');
	background-attachment: fixed;
	background-size: cover;
	background-position: bottom;
}

.Mobile_Middle_Banner {
	width: 100%;
	background: rgba(0, 0, 0, .3);
	padding: 0 15px 30px;
}

.Mobile_Middle_Banner img {
	width: 100%;
	margin-bottom: 15px;
}

.MM_Login_Register_Btn_Container img {
	width: 50%;
	padding: 0 1px;

}

.MM_Small_Text_Container {
	width: 50%;
}

.RB_Cash_Btn_Container {
	width: 50%;
}

.MM_Small_Text_Container p {
	font-size: 12px;
}

.MM_Small_Btn_Container {
	display: flex;
	flex-wrap: wrap;
}

.MM_Small_Btn_Container img {
	width: 50%;
	margin-bottom: 2px
}

.Middle_Banner_Container {
	padding: 0px 15px 30px;
}

.MB_Img_Gallery {
	margin: 10px 0px;
}

.MB_Img {
	display: flex;
	flex-wrap: wrap;

}

.MB_Img img {
	/* padding: 0 15px 30px; */
	background-size: cover;
	background-position: center;
	background-repeat: no-repeat;
	border-radius: 12px;
	border: 1px solid #fff;
}

@media screen and (max-width: 576px) {
	.MB_Img img {
		width: 33%;
	}
}

.Middle_Inner_Container a {
	padding: 0;
	color: rgba(13, 110, 253);
}

.google-map-link {
	font-style: italic;
	color: #f0d843 !important;
	font-weight: bolder;
	font-size: 12px;
	overflow-wrap: anywhere;
}

.map-container {
	display: flex;
	justify-content: flex-start;
	align-items: center;
	margin: 20px 0;
}

.platform {
	color: #f0d843 !important;
}

.running-sentence-container {
	width: 100%;
	overflow: hidden;
	position: relative;
	background-image: url('/public/images/Running_Banner_BgImg.gif');
	visibility: visible;
	background-size: 100% 100%;
	background-color: black;
	color: #f3c015;
	font-size: 12px;
}

.running-sentence {
	white-space: nowrap;
	/* position: absolute; */
	width: max-content;
	animation: scroll 40s linear infinite;
}

@keyframes scroll {
	0% {
		transform: translateX(75%);
	}

	100% {
		transform: translateX(-100%);
	}
}

.site-tabs {
	display: flex;
	flex-wrap: wrap;
	margin: 10px 0;
}

.image-container {
	width: 6.66%;
	cursor: pointer;
}

.image-container img {
	width: 100%;
}

@media (max-width: 768px) {
	.site-tabs {
		flex-wrap: nowrap;
		overflow-x: auto;
		/* Allow horizontal scrolling */
		-webkit-overflow-scrolling: touch;
		/* Enable smooth scrolling on touch devices */
	}

	.image-container {
		width: 71px;
		/* Fixed width for mobile view */
		flex: 0 0 auto;
		/* Prevent shrinking */
	}

	.site-tabs::-webkit-scrollbar {
		display: none;
		/* Hide scrollbar on WebKit browsers */
	}

	.site-tabs {
		-ms-overflow-style: none;
		/* Hide scrollbar on IE and Edge */
		scrollbar-width: none;
		/* Hide scrollbar on Firefox */
	}
}

.image-grid-container {
	display: grid;
	gap: 10px;
}

@media (min-width: 1200px) {
	.image-grid-container {
		grid-template-columns: repeat(6, 1fr);
	}
}

@media (min-width: 768px) and (max-width: 1199px) {
	.image-grid-container {
		grid-template-columns: repeat(4, 1fr);
	}
}

@media (max-width: 767px) {
	.image-grid-container {
		grid-template-columns: repeat(3, 1fr);
	}
}

.image-wrapper img {
	width: 100%;
}

.image-wrapper button {
	border-radius: 30px;
	padding: 3px 0;
	margin-top: 8px;
	width: 100%;
	border: 1px solid #34740e;
	background-color: #4ba614;
	background-image: linear-gradient(to bottom, #4ba614, #008c00);
	text-align: center;
	color: white;
	font-size: 11px;
	margin-bottom: 10px;
}

.image-wrapper p {
	margin-bottom: 0;
}

.footer-content {
	margin-bottom: 60px;
}

.footer-content h2,
p {
	color: white;
}
</style>
