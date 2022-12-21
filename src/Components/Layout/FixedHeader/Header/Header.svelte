<script>
  import SearchBar from "./SearchBar/SearchBar.svelte";
  import HeaderFragments from "./HeaderFragments/HeaderFragments.svelte";
  import Banner from "./Banner/Banner.svelte";
</script>

<div class='header'>
  <Banner></Banner>
  <SearchBar></SearchBar>
  <HeaderFragments></HeaderFragments>
</div>

<style>
  .header{
    display: flex;
    width: 100%;
    height: 75px;
    background: white;
    /* margin: 0rem 0 0 1rem; */
  }
</style>

