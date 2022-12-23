<script>
  import megaMenu from '../../../../../Data/megaMenu.json';


  let showMobileMenu = false;
  const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);
</script>


  {#if showMobileMenu }
    <div class="navbar-list"> 
      {#each megaMenu?.data as {title} }
        <div class='magaMenu'>
          <span>{title}</span>
        </div>
      {/each}
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={handleMobileIconClick} class={`mobile-icon active`}>
          <div class="middle-line"></div>
    </div>
    {:else}
      <div class="mobile-hamberger-icon">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div on:click={handleMobileIconClick} class={`mobile-icon`}>
          <div class="middle-line"></div>
        </div>
        <span class="hamberger-text" >Menu</span>
       </div>
    {/if}
<style>
  .navbar-list{
    display: flex;
    position: fixed;
    width: 90%;
    z-index: 20;
    background: #eff1f3;
    height: 100%;
    flex-direction: column;
    justify-content: space-around;
  }
  .navbar-list .magaMenu{
    font-size: 1.15em;
    text-align: left;
    text-transform: uppercase;
    font-weight: bold;
    padding: 0.5rem 5rem;
  }
  .mobile-hamberger-icon{
    padding: 3%;
  }
  .hamberger-text{
    font-size: 10px;
    text-transform: uppercase;
    font-weight: bold;
  }
  .mobile-icon {
    width: 25px;
    height: 14px;
    position: relative;
    cursor: pointer;
    margin: auto;
  }

  .mobile-icon:after,
  .mobile-icon:before,
  .middle-line {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
  background-color: rgb(37, 37, 37);
    transition: all 0.4s;
    transform-origin: center;
  }

  .mobile-icon:before,
  .middle-line {
    top: 0;
  }

  .mobile-icon:after,
  .middle-line {
    bottom: 0;
  }

  .mobile-icon:before {
    width: 100%;
  }

  .mobile-icon:after {
    width: 100%;
  }

  .middle-line {
    margin: auto;
  }

  .mobile-icon.active{
    height: 25px;
    position: fixed;
    right: 10px;
    top: 10px;
    color: black;
  }
  .mobile-icon:hover:before,
  .mobile-icon:hover:after,
  .mobile-icon.active:after,
  .mobile-icon.active .middle-line {
     width: 100%;
  }
  .mobile-icon.active:before,
  .mobile-icon.active:after {
    top: 50%;
    transform: rotate(-45deg);
  }

  .mobile-icon.active .middle-line {
    transform: rotate(45deg);
  } 
</style>