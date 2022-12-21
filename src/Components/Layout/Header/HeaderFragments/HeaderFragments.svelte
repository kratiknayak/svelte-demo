<script>
  import headerFragments from '../../../../Data/headerFragments.json';
</script>
<div class="headerFragments-row">
  {#each headerFragments?.data as {title, icon} }
    <div class='headerFragment'>
      <span >
        <img style:height='30px' src={icon} alt={title}>
      </span>
      <span>{title}</span>
    </div>
  {/each}
</div>

<style>
  .headerFragments-row{
    display: flex;
    flex:2;
  }
  .headerFragment{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: 300;
    font-size: small;
    padding: 0px 10px;
  }
</style>