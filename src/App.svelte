<script>
	import Header from "./Components/Layout/FixedHeader/Header/Header.svelte";
	import MegaMenu from "./Components/Layout/FixedHeader/MegaMenu/MegaMenu.svelte";
	import Carousel from "./Components/Layout/Content/Carousel/Carousel.svelte";
	import Category from "./Components/Layout/Content/Category/Category.svelte";
	import GiftIdea from "./Components/Layout/Content/GiftIdea/GiftIdea.svelte";
  import FixedHeader from "./Components/Layout/FixedHeader/FixedHeader.svelte";
  import Content from "./Components/Layout/Content/Content.svelte";
</script>

<FixedHeader>
	<Header slot="header"></Header>
	<MegaMenu  slot="megaMenu"></MegaMenu>
</FixedHeader>
<Content>
	<Carousel slot="carousel"></Carousel>
	<Category slot="category"></Category>
	<GiftIdea slot="giftIdea" ></GiftIdea>
</Content>

