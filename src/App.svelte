<script>
	import Header from "./Components/Layout/Header/Header.svelte";
	import MegaMenu from "./Components/Layout/MegaMenu/MegaMenu.svelte";
	import Carousel from "./Components/Layout/Carousel/Carousel.svelte";
	import Category from "./Components/Layout/Category/Category.svelte";
	import GiftIdea from "./Components/Layout/GiftIdea/GiftIdea.svelte";
</script>


<div>
		<Header></Header>
		<MegaMenu></MegaMenu>
		<!-- <Carousel></Carousel> -->
		<Category></Category>
		<GiftIdea></GiftIdea>
</div>

<style>
	/* div {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		div {
			max-width: none;
		}
	} */
</style>
