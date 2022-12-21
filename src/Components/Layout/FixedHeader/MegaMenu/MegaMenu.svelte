<script>
  import { onMount } from 'svelte';
  import megaMenu from '../../../../Data/megaMenu.json';
  let activeHover = ''
  // Show mobile icon and display menu
  let showMobileMenu = false;
  
  // Mobile menu click event handler
  const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);

  // Media match query handler
  const mediaQueryHandler = e => {
    // Reset mobile state
    if (!e.matches) {
      showMobileMenu = false;
    }
  };
  onMount(() => {
    const mediaListener = window.matchMedia("(max-width: 767px)");

    mediaListener.addListener(mediaQueryHandler);
  });
</script>


  <div class="inner">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={handleMobileIconClick} class={`mobile-icon${showMobileMenu ? ' active' : ''}`}>
      <div class="middle-line"></div>
    </div>
    <div class={`navbar-list ${showMobileMenu ? ' mobile' : ''}`}>
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

  /* nav { */
  /* font-family: "Helvetica Neue", "Helvetica", "Arial", sans-serif; */
  /* height: 45px; */
/* } */

/* .inner { */
  /* max-width: 980px; */
  /* padding-left: 20px; */
  /* padding-right: 20px; */
  /* margin: auto; */
  /* box-sizing: border-box; */
  /* display: flex; */
  /* align-items: center; */
  /* height: 100%; */
/* } */

.mobile-icon {
  width: 25px;
  height: 14px;
  position: relative;
  cursor: pointer;
}

.mobile-icon:after,
.mobile-icon:before,
.middle-line {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  background-color: rgb(0, 0, 0);
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

.mobile-icon:hover:before,
.mobile-icon:hover:after,
.mobile-icon.active:before,
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

.navbar-list {
  display: none;
  width: 100%;
  justify-content: space-between;
  margin: 0;
  padding: 0 40px;
}

.navbar-list.mobile {
  background-color: #eff1f3;
  position: fixed;
  display: block;
  height: calc(100% - 45px);
  bottom: 0;
  left: 0;
}



@media only screen and (min-width: 767px) {
  .mobile-icon {
    display: none;
  }

  .navbar-list {
    display: flex;
    padding: 0;
  }

  /* .navbar-list a {
    display: inline-flex;
  } */
}
</style>