<script>
  import category from '../../../../Data/category.json';
  import { lazyLoad } from '../../../../Utils/lazyLoad';
</script>
<div class="category-row">
  {#each category?.data as {title,image} }
    <div class='category' >
      <div class='img-holder'>
         <img use:lazyLoad={image}  src="loading.svg" class='category-img'   alt={title}> 
      </div>
      <span> {title}</span>
    </div>
  {/each}
</div>

<style>
  .category-row{
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: repeat(auto-fill, minmax(13rem, 1fr));
    margin: 3rem 0; 
  }
  .category{
    cursor: pointer;
    background-color: #eff1f3;
    display: flex;
    align-items: center;
    /* padding: 0% 3% 0% 0%; */
    border-radius: 8px;
    font-weight: 700;
  }
  .img-holder{
    width: 5.5rem;
    min-width: 5.5rem;
    height: 5.5rem;
  }
  .category-img{
    height: 100%;
  }
</style>