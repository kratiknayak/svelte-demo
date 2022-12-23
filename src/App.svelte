<script>
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
{#if innerWidth < 888}
	<FixedMobileHeader/>
{:else}
	<FixedHeader/>
{/if}
<Content>
	<Carousel slot="carousel"></Carousel>
	<Category slot="category"></Category>
	<GiftIdea slot="giftIdea" ></GiftIdea>
</Content>

