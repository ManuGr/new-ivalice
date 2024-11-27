<script lang="ts">
	import '../app.css';
	let { children } = $props();

	const links = [
		{title: "Home", url: "/"},
		{title: "Dialog", url: "/dialog"},
		{title: "Map", url: "/map"}
	]
</script>

<nav class="flex justify-between items-center fixed w-full px-4 bg-blue-400">
	<a href="/" class="text-lg text-white font-semibold">
		Manuel Grgic
	</a>
	<ul class="flex">
		{#each links as link}
			<li class="text-white p-2 font-semibold h-full hover:bg-blue-500">
				<a href={link.url}>{link.title}</a>
			</li>
		{/each}
	</ul>
</nav>

{@render children()}
