<script>
  import { lazyLoad } from "../../../../../Utils/lazyLoad";
  let decathlonLogo = "https://contents.mediadecathlon.com/s967801/.png?format=auto&f=969x0"
</script>

<div class="banner">
  <img  use:lazyLoad={decathlonLogo} alt='decathlon logo' src="loading.svg">
</div>

<style>
  .banner{
    flex:4;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  img{
    height:100%;
  }
</style>