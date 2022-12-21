<script>
  import category from '../../../Data/category.json';
  import { lazyLoad } from '../../../Utils/lazyLoad';
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
    display: flex;
    justify-content:space-between;
    max-height: 100px;
  }
  .category{
    cursor: pointer;
    background-color: #eff1f3;
    display: flex;
    align-items: center;
    padding: 0% 3% 0% 0%;
    border-radius: 8px;
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