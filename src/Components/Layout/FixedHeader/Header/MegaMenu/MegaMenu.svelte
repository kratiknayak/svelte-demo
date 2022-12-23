<script>
  import megaMenu from '../../../../../Data/megaMenu.json';
  let activeHover = ''
</script>


  <div class="inner">
   
    <div class="navbar-list ">
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
  .navbar-list{
    display: flex;
    justify-content: space-between;
    background: white;
    padding: 0% 5%;
  }
  .magaMenu{
    padding: 2%;
    cursor: pointer;
  }
  @media only screen and (max-width: 595px) {}

  /* Small screen devices (600px and above) */
  @media only screen and (min-width: 600px) and (max-width:767px) {
   
  }

  /* Medium screen devices (768px and above) */
  @media only screen and (min-width: 768px)  and (max-width:888px) {
    /* .navbar-list{
      display: none;
    } */
  }

  /* Big screen devices (889px and above) */
  @media only screen and (min-width: 889px) and (max-width:1999px) {
  
  }

  /* Extra big screen devices (1200px and above) */
  @media only screen and (min-width: 1200px) {

  }
</style>