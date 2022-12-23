<script>
  import MobileHeader from "./MobileHeader/MobileHeader.svelte";
  import MobileMegaMenu from "./MobileHeader/MobileMegaMenu/MobileMegaMenu.svelte";
  import SearchBar from "./MobileHeader/SearchBar/SearchBar.svelte";
</script>

<div class="fixed-mobile-header" >
    <MobileHeader></MobileHeader>
    <SearchBar></SearchBar>
</div>

<style>
  .fixed-mobile-header{
    position: sticky;
    top: 0;
    border-bottom: 1px solid #bcbcbc6b;
    z-index: 10;
    background: white;
  }

</style>