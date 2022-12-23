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
      <span class="title">{title}</span>
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
    justify-content: right;
  }
  .headerFragment{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: 300;
    font-size: 10px;
    padding: 0px 10px;
    text-transform: uppercase;
  }

  /* Small screen devices (600px and above) */
  @media only screen and (min-width: 600px) and (max-width:767px) {
    .title{
      display: none;
    }
  }

  /* Medium screen devices (768px and above) */
  @media only screen and (min-width: 768px)  and (max-width:888px) {
    .title{
      display: none;
    }
  }

  /* Big screen devices (889px and above) */
  @media only screen and (min-width: 889px) and (max-width:1999px) {
    .title{
      font-size:8px ;
    }
    .headerFragments-row{
      flex:4;
    }
  }

  
</style>