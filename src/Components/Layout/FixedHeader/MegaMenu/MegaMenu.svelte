<script>
  import megaMenu from '../../../../Data/megaMenu.json';
  let activeHover = ''
</script>
<div class="magaMenu-row">
  {#each megaMenu?.data as {title,identifier} }
    <div class='magaMenu' class:active={activeHover === identifier} 
      class:blue={identifier ==='Tous_les_sports'}
      class:red={identifier ==='Promotions'}
      class:green={identifier ==='Seconde_vie'}
      on:mouseenter={() => {
        activeHover = identifier
      }} 
      on:mouseleave={() => {
        activeHover = ''
      }}>
      <span>{title}</span>
      <span> &#9660;</span>
    </div>
  {/each}
</div>

<style>
  .active{
    color: #007dbc;
  }
  .red{
    color: #e32630;
    font-weight: bolder;
  }
  .green{
    color: #4D6F56;
    font-weight: bolder;
  }
  .blue{
    color: #007dbc;
    font-weight: bolder;
  }
  .magaMenu-row{
    display: flex;
    justify-content: space-between;
    background: white;
    padding: 0% 5%;
  }
  .magaMenu{
    padding: 1%;
    cursor: pointer;
  }
</style>