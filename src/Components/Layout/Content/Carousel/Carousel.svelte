<script>
   import carousel from '../../../../Data/carousel.json';
  import { lazyLoad } from '../../../../Utils/lazyLoad';
  import ImageContainer from './ImageContainer/ImageContainer.svelte';
   console.log(carousel.data)
</script>

 

<ImageContainer autoplay="4000">
  {#each carousel?.data as {image,buttonText,title}, index (index)}
      <div class="carousel">
        <div class="carousel-text">
          <h3>{title}</h3>  
          <button type="button">{buttonText}</button>
        </div>
	      <img use:lazyLoad={image}  src="loading.svg" alt={title} />
      </div>
	{/each}
</ImageContainer>

<style>
  img{
    filter: brightness(0.7);
    border-radius: 8px;
    width: 100%;
    height: 70vh;
  }
  .carousel{
    position: relative;
    
  }
  .carousel-text{
    position: absolute;
    left: 0;
    bottom: 0;
    margin: 1.2rem 1.2rem;
    color: white;
    width:40%;
    z-index: 5;
  }
  h3{
    font-size: 40px;
    font-weight: 700;
    line-height: 44px;
    text-align: left;
    margin-bottom: 15px;
  }
  button{
    letter-spacing: .027rem;
    border-radius: 4px;
    padding: 10px 20px;
    background-color:#ffe928;
    box-shadow: inset 0 0 0 0.2rem transparent;
    color:#001018;    
    font-size: 1.1rem;
    font-weight: 700;

  }
</style>