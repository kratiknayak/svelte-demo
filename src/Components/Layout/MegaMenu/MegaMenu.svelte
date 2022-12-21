<script>
  import megaMenu from '../../../Data/megaMenu.json';
</script>
<div class="magaMenu-row">
  {#each megaMenu?.data as {title} }
    <div class='magaMenu' >
      <span>{title}</span>
      <span> &#9662;</span>
    </div>
  {/each}
</div>

<style>
  .magaMenu-row{
    display: flex;
    justify-content: space-between;
  }
  .magaMenu{
    padding: 1%;
    cursor: pointer;
  }
</style>