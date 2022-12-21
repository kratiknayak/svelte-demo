<script>
  import giftIdea from '../../../../Data/giftIdea.json';
  import { lazyLoad } from '../../../../Utils/lazyLoad';
</script>

<div>
  <h2>Nos idées cadeaux de Noël</h2>
  <div class="giftIdea-row">
    {#each giftIdea?.data as {title,image} }
      <div class='giftIdea' >
        <div class='img-holder'>
          <img use:lazyLoad={image}  src="loading.svg" class='giftIdea-img'   alt={title}> 
        </div>
        <span class="title"> {title}</span>
      </div>
    {/each}
  </div>
</div>

<style>
  .giftIdea-row{
    display: flex;
    justify-content: space-between;
  }
  .giftIdea{
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: left;
    border-radius: 8px;
    /* min-width: calc(100% / 6); */
  }
  .img-holder{
    min-width: 9rem;
    height: 17rem;
  }
  .title{
    line-height: 1.3;
    font-style: italic;
    text-transform: uppercase;
    font-weight: 700;
    text-align: left;
    margin-top: 5px;
    font-family: Roboto Condensed,Arial Narrow,sans-serif;
  }
  .giftIdea-img{
    height: 100%;
    border-radius: 10px;
  }
</style>