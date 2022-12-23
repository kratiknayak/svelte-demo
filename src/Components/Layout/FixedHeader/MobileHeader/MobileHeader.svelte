<script>
  import Banner from "./Banner/Banner.svelte";
  import HeaderFragments from "./HeaderFragments/HeaderFragments.svelte";
</script>

<div class='header-row'>
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

