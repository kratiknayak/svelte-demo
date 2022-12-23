<script>
  import Banner from "./Banner/Banner.svelte";
  import HeaderFragments from "./HeaderFragments/HeaderFragments.svelte";
  import MobileMegaMenu from "./MobileMegaMenu/MobileMegaMenu.svelte";
</script>

<div class='header-row'>
  <MobileMegaMenu/>
  <Banner></Banner>
  <HeaderFragments></HeaderFragments>
</div>

<style>
  .header-row{
    display: flex;
    width: 100%;
    height: 60px;
    background: white;
  }
</style>

