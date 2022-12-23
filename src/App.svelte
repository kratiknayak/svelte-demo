<script>
	// import Header from "./Components/Layout/FixedHeader/Header/Header.svelte";
	// import MobileHeader from "./Components/Layout/FixedHeader/MobileHeader/MobileHeader.svelte";
	// import MobileMegaMenu from "./Components/Layout/FixedHeader/MobileMegaMenu/MobileMegaMenu.svelte";
	// import MegaMenu from "./Components/Layout/FixedHeader/MegaMenu/MegaMenu.svelte";
	import Carousel from "./Components/Layout/Content/Carousel/Carousel.svelte";
	import Category from "./Components/Layout/Content/Category/Category.svelte";
	import GiftIdea from "./Components/Layout/Content/GiftIdea/GiftIdea.svelte";
  import FixedHeader from "./Components/Layout/FixedHeader/FixedHeader.svelte";
  import FixedMobileHeader from "./Components/Layout/FixedHeader/FixedMobileHeader.svelte";
  import Content from "./Components/Layout/Content/Content.svelte";
	$: innerWidth = innerWidth
  $: innerHeight = innerWidth
</script>
<svelte:window bind:innerWidth bind:innerHeight />
{#if innerWidth < 767}
	<FixedMobileHeader/>
{:else}
	<FixedHeader/>
{/if}
<Content>
	<Carousel slot="carousel"></Carousel>
	<Category slot="category"></Category>
	<GiftIdea slot="giftIdea" ></GiftIdea>
</Content>

