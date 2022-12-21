<script>
  import headerFragments from '../../../../../Data/headerFragments.json';
  let activeHover = ''
</script>
<div class="headerFragments-row">
  {#each headerFragments?.data as {title, icon,identifier} }
    <div class='headerFragment' 
      class:active={activeHover === identifier && identifier != 'cart'} 
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
      <span>{title}</span>
    </div>
  {/each}
</div>

<style>
  .active{
    border-top:2px solid #007dbc ;
  }
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