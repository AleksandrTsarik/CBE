<template>
	<header class="header">
		<div class="header-info wrapper">
			<div class="header__logo"><TheNetwork :type="'logo'" /></div>
			<nav class="header-info__list">
				<ul>
					<li v-for="(item, i) in infoList" :key="i">
						<NuxtLink class="header-info__item"  :to="item.url">{{ item.name }}</NuxtLink>
					</li>
				</ul>
				<NuxtLink class="header__phone" to="tel:88007001996">8 800 700 1996</NuxtLink>
				
			</nav>
			<div class="burger" @click="menuOpen" :class="{'is-open': isOpenMenu}">
				<span></span>
				<span></span>
				<span></span>
			</div>
			<div class="header-overlay" :class="{'is-open': isOpenMenu}"></div>
			<div class="header-drop" :class="{'is-open': isOpenMenu}">
				<div class="header-drop__list">
					<ul>
						<li v-for="(item, i) in infoList" :key="i">
							<NuxtLink class="header-info__item"  :to="item.url">{{ item.name }}</NuxtLink>
						</li>
					</ul>
					<NuxtLink class="header__phone" to="tel:88007001996">8 800 700 1996</NuxtLink>
					<nav class="header-nav">
						<ul class="header-nav__list">
							<li class="header-nav__item" v-for="(item, i) in navList" :key="i">
								<NuxtLink :to="item.url" :class="item.program ? 'is-children' : '' ">{{ item.name }}</NuxtLink>
								<ul v-if="item.program" class="header-nav-sublist">
									<li v-for="(p, i) in item.program" :key="i">
										<NuxtLink :to="p.url">{{ p.programName }}</NuxtLink>
									</li>
								</ul>
							</li>
						</ul>
					</nav>
					<div class="header-strip__btn">
						<UITheButton :label="'Календарь программ'" class="btn btn-small btn-small__dark" />
					</div>
				</div>
			</div>
		</div>

		<div class="header-strip">
			<div class="wrapper header-strip__inner">
				<nav class="header-nav">
					<ul class="header-nav__list">
						<li class="header-nav__item" v-for="(item, i) in navList" :key="i">
							<NuxtLink :to="item.url" :class="item.program ? 'is-children' : '' ">{{ item.name }}</NuxtLink>
							<ul v-if="item.program" class="header-nav-sublist">
								<li v-for="(p, i) in item.program" :key="i">
									<NuxtLink :to="p.url">{{ p.programName }}</NuxtLink>
								</li>
							</ul>
						</li>
					</ul>
				</nav>
				<div class="header-strip__btn">
					<UITheButton :label="'Календарь программ'" class="btn btn-small btn-small__dark" />
				</div>
			</div>
		</div>
		

	</header>
</template>

<script>
export default {
	data() {
		return {
			isOpenMenu: false,
			infoList: [
				{
					name: 'О бизнес-школе',
					url: '#'
				},
				{
					name: 'Партнерство',
					url: '#'
				},
				{
					name: 'Реквизиты',
					url: '#'
				},
			],
			navList: [
				{
					name: 'Все программы',
					url: '#',
					program: [
						{
							programName: 'Lorem',
							url: '#'
						},
						{
							programName: 'Lorem',
							url: '#'
						},
						{
							programName: 'Lorem',
							url: '#'
						},
						{
							programName: 'Lorem',
							url: '#'
						}
					]
				},
				{
					name: 'MBA',
					url: '#',
				},
				{
					name: 'Корпоративное обучение',
					url: '#',
				},
				{
					name: 'Клуб ЦБО',
					url: '#',
				},
				{
					name: 'Молодежная Бизнес Лига',
					url: '#',
				},
				{
					name: 'Интеллектуальные путешествия',
					url: '#',
				},
				
			]
		}
	},
	methods: {
		menuOpen() {
			if (!this.isOpenMenu) document.body.classList.add('menu-open')
			else document.body.classList.remove('menu-open')
			this.isOpenMenu = !this.isOpenMenu
		}
	}
}
</script>

<style lang="scss">
.header {
	background-color: #F7F7F8;
	position: fixed;
	left: 0;
	right: 0;
	top: 0;
	z-index: 100;
	// &::after {
  //   content: '';
  //   display: block;
  //   height: 30px;
  //   width: 100%;
  //   background-image: linear-gradient(to bottom, #a4fdff -100%, rgba(red, .005));
  //   position: absolute;
  //   left: 0;
  //   right: 0;
  //   bottom: -30px;
  //   margin: 0 auto;
	// }
	&__phone {
		color: var(--green2);
		font-size: 16px;
		font-weight: 700;
		margin-left: 30px;
		line-height: 140%;
		@media(max-width: 767px) {
			margin-left: 0;
			margin-bottom: 20px;
			display: block;
		}
	}
}
.header-info {
	display: grid;
	grid-template-columns: 130px 1fr;
	justify-content: space-between;
	align-items: center;
	padding-top: 20px;
	padding-bottom: 20px;
	&__list {
		margin-left: auto;
		display: flex;
		align-items: center;
		@media(max-width: 767px) {
			display: none;
		}
		ul {
			display: flex;
			align-items: center;
		}
	}
	&__item {
		margin-left: 25px;
		color: var(--grey3);
		transition: 0.3s;
		@media(max-width: 767px) {
			margin-left: 0;
		}
		&:active {
			color: var(--lightGreen);
		}
		&:hover {
			@media(min-width: 1024px) {
				color: var(--lightGreen);
			}
		}
	}
}
.header-strip {
	background: var(--green);
	color: var(--white);
	padding: 20px 0;
	@media(max-width: 767px) {
		display: none;
	}
	a {
		color: var(--white);
	}
	&__inner {
		display: grid;
		grid-template-columns: 1fr auto;
		gap: 120px;
		align-items: center;
		justify-content: space-between;
		@media(max-width: 1023px) {
			gap: 50px;
		}
	}
	&__btn {
		margin-left: auto;
		@media(max-width: 767px) {
			button {
				width: 100%;
				display: block;
			}
		}
	}
}
.header-nav-sublist {
	position: absolute;
	box-shadow: 0 0 5px rgba(0,0,0,0.5);
	background-color: var(--white);
	width: 100%;
	max-width: 500px;
	column-count: 2;
	display: none;
	transition: 0.3s;
	li {
		padding: 10px;
		break-inside: avoid;
		transition: 0.3s;
		a {
			color: var(--green);
			display: block;
		}
		&:hover {
			@media(min-width: 1024px) {
				background-color: var(--bg);
			}
		}
	}
}
.header-nav {
	overflow-x: auto;
	&::-webkit-scrollbar {
		height: 1px;
	}
	&__list {
		display: flex;
		align-items: center;
		justify-content: space-between;
		@media(max-width: 767px) {
			display: block;
		}
	}
	&__item {
		margin-right: 10px;
		white-space: nowrap;
		a {
			transition: 0.2s;
			position: relative;
			@media(max-width: 767px) {
				color: var(--green2);
			}
			&:hover {
				@media(min-width: 1024px) {
					color: var(--lightGreenHover);
				}
			}
		}
		&:hover {
			.header-nav-sublist {
				@media(min-width: 1024px) {
					display: block;
				}
			}
				
			}
		.is-children {
			position: relative;
			display: block;
			margin-right: 10px;
			&::after {
				content: '';
				display: block;
				width: 7px;
				height: 7px;
				border-right: solid 2px;
				border-bottom: solid 2px;
				position: absolute;
				right: -10px;
				top: 50%;
				transition: 0.2s;
				transform: translateY(-50%) rotate(45deg);
			}
		}
	}
}
.burger {
	flex-direction: column;
	justify-content: space-between;
	flex: 0 0 30px;
	width: 30px;
	max-width: 30px;
	height: 20px;
	cursor: pointer;
	position: relative;
	display: none;
	z-index: 200;
	@media(max-width: 767px) {
		display: flex;
		margin-left: auto;
	}
	span {
		display: block;
		width: 100%;
		background-color: var(--grey);
		height: 2px;
		border-radius: 50px;
		transition: 0.5s;
		transform: rotate(180deg);
	}
	&.is-open {
		span {
			position: absolute;
			left: 0;
			top: 7px;
			transition: 0.5s;
			//transform: rotate(45deg);
			&:nth-child(1) {
				transform: rotate(45deg);
			}
			&:nth-child(2) {
				opacity: 0;
			}
			&:nth-child(3) {
				transform: rotate(-45deg);

			}
		}
	}
}
.header-drop {
	position: fixed;
	top: 0;
	right: -100%;
	transition: 0.3s;
	bottom: 0;
	height: 100%;
	background-color: #fff;
	opacity: 0;
	width: 0;
	&__overlay {

	}
	&.is-open {
		opacity: 1;
		max-width: 350px;
		width: 100%;
		right: 0;
		padding: 20px;
		background-color: #fff;
		z-index: 150
	}
	&__list {
		margin-top: 40px;
		z-index: 100;
		position: relative;
		z-index: 150;
		li {
			margin-bottom: 10px;
			a {
				color: var(--green2);
			}
		}
	}
}
.header-overlay {
	background-color: rgba(black, 0.5);
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	height: 100%;
	display: none;
	z-index: 0;
	&.is-open {
		display: block;
	}
}
</style>