<script>
  import SearchBar from "./SearchBar/SearchBar.svelte";
  import HeaderFragments from "./HeaderFragments/HeaderFragments.svelte";
  import Banner from "./Banner/Banner.svelte";
</script>

<div class='header-row'>
  <Banner></Banner>
  <SearchBar></SearchBar>
  <HeaderFragments></HeaderFragments>
</div>

<style>
  .header-row{
    display: flex;
    width: 100%;
    height: 75px;
    background: white;
  }
</style>

