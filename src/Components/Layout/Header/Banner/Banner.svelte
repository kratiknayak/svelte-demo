<script>
  import { lazyLoad } from "../../../../Utils/lazyLoad";
  let decathlonLogo = "https://contents.mediadecathlon.com/s967801/.png?format=auto&f=969x0"
</script>

<div class="banner">
  <img style:height='100%' use:lazyLoad={decathlonLogo} alt='decathlon logo' src="loading.svg">
</div>

<style>
  .banner{
    flex:1;
  }
</style>