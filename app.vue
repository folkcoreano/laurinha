<script setup>
const {data} = useFetch("https://api.kanye.rest/text");
</script>

<template>
	<div class="back">
		<Head>
			<Title>{{ data }}</Title>
			<Link
				rel="icon"
				href="/favicon.png"
			/>
			<Meta
				name="title"
				:content="data"
			/>
			<Meta
				name="description"
				:content="data"
			/>
			<Meta
				property="og:type"
				content="website"
			/>
			<Meta
				property="og:title"
				:content="data"
			/>
			<Link
				rel="stylesheet"
				href="main.css"
			/>
			<Meta
				property="og:description"
				:content="data"
			/>
			<Meta
				property="og:image"
				:content="'https://cdn.statically.io/og/theme=dark/' + data + '.png'"
			/>
			<Meta
				property="twitter:card"
				content="summary_large_image"
			/>
			<Meta
				property="twitter:title"
				:content="data"
			/>
			<Meta
				property="twitter:description"
				:content="data"
			/>
			<Meta
				property="twitter:image"
				:content="'https://cdn.statically.io/og/theme=dark/' + data + '.png'"
			/>
		</Head>
		<i class="quote">
			<q>{{ data }}</q>
		</i>
		<img
			src="/favicon.png"
			alt="laurinha"
		/>
	</div>
</template>

<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: system-ui;
}

@keyframes tilt {
	0% {
		transform: rotate(-5deg);
	}
	50% {
		transform: rotate(5deg);
	}
	100% {
		transform: rotate(-5deg);
	}
}

@-webkit-keyframes color-change-5x {
	0% {
		background: #19dcea;
	}

	25% {
		background: #b22cff;
	}

	50% {
		background: #ea2222;
	}

	75% {
		background: #f5be10;
	}

	100% {
		background: #3bd80d;
	}
}

@keyframes color-change-5x {
	0% {
		background: #19dcea;
	}

	25% {
		background: #b22cff;
	}

	50% {
		background: #ea2222;
	}

	75% {
		background: #f5be10;
	}

	100% {
		background: #3bd80d;
	}
}

html,
body {
	height: 100%;
}

body {
	background-color: #111;
	color: #eee;
	display: flex;
	overflow: hidden;
	align-items: center;
	justify-content: center;
	-webkit-animation: color-change-5x 8s linear infinite alternate both;
	animation: color-change-5x 8s linear infinite alternate both;
}

body div:first-child {
	display: flex;
	flex-flow: column;
	align-items: center;
	justify-content: center;
}

img {
	z-index: 1;
	padding: 2rem;
	position: relative;
	max-width: 100%;
	animation: tilt infinite alternate ease 1000ms;
	transform: rotate(0deg);
	transition: all 150ms ease;
}

q {
	text-shadow: 2px 2px 10px #000;
}

.quote {
	font-weight: bold;
	font-size: 1.55rem;
	position: fixed;
	z-index: 2;
	display: flex;
	align-items: center;
	justify-content: center;
	max-width: 50rem;
}

.back {
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	z-index: 0;
	position: fixed;
	background-image: url(/favicon.png);
	background-repeat: repeat;
	background-size: 10rem;
	background-position: center;
}
</style>
