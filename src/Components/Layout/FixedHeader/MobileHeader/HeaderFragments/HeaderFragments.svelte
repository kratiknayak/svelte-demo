<script>
  import headerFragments from '../../../../../Data/headerFragments.json';
  let activeHover = ''
</script>
<div class="headerFragments-row">
  {#each headerFragments?.mobileData as {title, icon,identifier} }
    <div class='headerFragment' 
      class:cart={identifier === 'cart'} 
      on:mouseenter={() => {
        activeHover = identifier
      }}
      on:mouseleave={() => {
        activeHover = ''
      }}>
      <span>
        <img  src={icon} alt={title}>
      </span>
    </div>
  {/each}
</div>

<style>
  .cart{
    background-color: #ffe928;
  }
  img{
    height: 30px;
  }
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