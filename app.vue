<script setup>
const {data} = useFetch("https://api.kanye.rest/text");
</script>

<template>
	<div>
		<Head>
			<Title>{{ data }}</Title>
			<Link
				rel="icon"
				href="https://api.iconify.design/twemoji/billed-cap.svg"
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
				:content="'https://cdn.statically.io/og/' + data + '.png'"
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
				:content="'https://cdn.statically.io/og/' + data + '.png'"
			/>
		</Head>
		<q>{{ data }}</q>
	</div>
</template>

<style>
html,
body {
	height: 100%;
}

body {
	background-color: #111;
	color: #eee;
	font-family: system-ui;
	display: flex;
	overflow: hidden;
	align-items: center;
	justify-content: center;
}

body div:first-child {
	display: flex;
	flex-flow: column;
	align-items: center;
	justify-content: center;
}
</style>
