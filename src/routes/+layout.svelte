<script lang="ts">
	import { dev } from "$app/environment";
	import { page } from "$app/stores";
	import { onMount } from "svelte";

	import { Navbar } from "$layout";
	import type { NavbarItem } from "$data/links";

	import "fluent-svelte/theme.css";

	import Home from "@fluentui/svg-icons/icons/home_24_regular.svg?raw";
	import News from "@fluentui/svg-icons/icons/news_24_regular.svg?raw";
	import History from "@fluentui/svg-icons/icons/history_24_regular.svg?raw";
	import PaintBrush from "@fluentui/svg-icons/icons/paint_brush_24_regular.svg?raw";
	import AppGeneric from "@fluentui/svg-icons/icons/app_generic_24_regular.svg?raw";

	const navbarItems: NavbarItem[] = [
	{
	name: "Home",
	path: "/",
	icon: Home
	},
	{
	name: "Blog",
	path: "/blog",
	icon: News
	}
	];

	const navbarButtons = [
	{
	icon: AppGeneric,
	href: "https://errortek.vercel.app/ute",
	label: "Visit the UTE subpage!",
	isExternal: false
	}
	];
</script>

<svelte:head>
	<meta content="ErrorTek's website" name="og:site_name" />
	<meta content="website" name="og:type" />
	<meta content="Dongle (original author), ErrorTek" name="author" />
	<meta content="#0078d4" name="theme-color" />

	{#if !dev}
		<script>
			(function (c, l, a, r, i, t, y) {
				c[a] =
					c[a] ||
					function () {
						(c[a].q = c[a].q || []).push(arguments);
					};
				t = l.createElement(r);
				t.async = true;
				t.src = "https://www.clarity.ms/tag/" + i;
				y = l.getElementsByTagName(r)[0];
				y.parentNode.insertBefore(t, y);
			})(window, document, "clarity", "script", "4q1wajdktz");
		</script>
	{/if}
</svelte:head>

<Navbar items={navbarItems} buttons={navbarButtons} />
<div class="background">
	<slot />
</div>

<style global lang="scss">
	@use "src/styles/global";
	@use "src/styles/markdown";
</style>
