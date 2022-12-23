<script>
  import Header from "./Header/Header.svelte";
  import MegaMenu from "./Header/MegaMenu/MegaMenu.svelte";
</script>

<div class="fixed-header" >
    <Header></Header>
		<!-- <MegaMenu></MegaMenu> -->
</div>

<style>
  .fixed-header{
    position: sticky;
    top: 0;
    border-bottom: 1px solid #bcbcbc6b;
    z-index: 10;
    background: white;
  }

</style>